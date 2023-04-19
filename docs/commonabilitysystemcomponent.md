## What is AbilitySystemComponent?
A component to easily interface with the 3 aspects of the AbilitySystem:

GameplayAbilities:

- Provides a way to give/assign abilities that can be used (by a player or AI for example)
- Provides management of instanced abilities (something must hold onto them)
- Provides replication functionality
- Ability state must always be replicated on the UGameplayAbility itself, but UAbilitySystemComponent provides RPC replication
for the actual activation of abilities

GameplayEffects:

- Provides an FActiveGameplayEffectsContainer for holding active GameplayEffects
- Provides methods for applying GameplayEffects to a target or to self
-  wrappers for querying information in FActiveGameplayEffectsContainers (duration, magnitude, etc)
- Provides methods for clearing/remove GameplayEffects

GameplayAttributes:

- Provides methods for allocating and initializing attribute sets
- Provides methods for getting AttributeSets

The Ability System Component (UAbilitySystemComponent) is the bridge between Actors and the Gameplay Ability System. Any Actor that intends to interact with the Gameplay Ability System needs its own Ability System Component, or access to an Ability System Component owned by another Actor. Make sure that your project is set up to use the Gameplay Ability System Pluginbefore attempting to use the Ability System Component. [Official Documentation](https://docs.unrealengine.com/5.0/en-US/gameplay-ability-system-component-and-gameplay-attributes-in-unreal-engine/)

The AbilitySystemComponent (ASC) is the heart of GAS. It's a UActorComponent (UAbilitySystemComponent) that handles all interactions with the system. Any Actor that wishes to use GameplayAbilities, have Attributes, or receive GameplayEffects must have one ASC attached to them. These objects all live inside of and are managed and replicated by (with the exception of Attributes which are replicated by their AttributeSet) the ASC. Developers are expected but not required to subclass this.

The Actor with the ASC attached to it is referred to as the OwnerActor of the ASC. The physical representation Actor of the ASC is called the AvatarActor. The OwnerActor and the AvatarActor can be the same Actor as in the case of a simple AI minion in a MOBA game. They can also be different Actors as in the case of a player controlled hero in a MOBA game where the OwnerActor is the PlayerState and the AvatarActor is the hero's Character class. Most Actors will have the ASC on themselves. If your Actor will respawn and need persistence of Attributes or GameplayEffects between spawns (like a hero in a MOBA), then the ideal location for the ASC is on the PlayerState.

Note: If your ASC is on your PlayerState, then you will need to increase the NetUpdateFrequency of your PlayerState. It defaults to a very low value on the PlayerState and can cause delays or perceived lag before changes to things like Attributes and GameplayTags happen on the clients. Be sure to enable Adaptive Network Update Frequency, Fortnite uses it.

Both, the OwnerActor and the AvatarActor if different Actors, should implement the IAbilitySystemInterface. This interface has one function that must be overriden, UAbilitySystemComponent* GetAbilitySystemComponent() const, which returns a pointer to its ASC. ASCs interact with each other internally to the system by looking for this interface function.

The ASC holds its current active GameplayEffects in FActiveGameplayEffectsContainer ActiveGameplayEffects.

The ASC holds its granted Gameplay Abilities in FGameplayAbilitySpecContainer ActivatableAbilities. Any time that you plan to iterate over ActivatableAbilities.Items, be sure to add ABILITYLIST_SCOPE_LOCK(); above your loop to lock the list from changing (due to removing an ability). Every ABILITYLIST_SCOPE_LOCK(); in scope increments AbilityScopeLockCount and then decrements when it falls out of scope. Do not try to remove an ability inside the scope of ABILITYLIST_SCOPE_LOCK(); (the clear ability functions check AbilityScopeLockCount internally to prevent removing abilities if the list is locked). [GASDocumentation](https://github.com/tranek/GASDocumentation#concepts-asc)
## Basic Requirements

To set up your AActor subclass to use the Gameplay Ability System, implement the IAbilitySystemInterface interface and override the GetAbilitySystemComponent function. This function must return the Ability System Component associated with your Actor. In most cases, the Actor class will have a variable, tagged with UPROPERTY, that stores a pointer to the Ability System Component, similar to any built-in Component on any Actor type. While it is common for an Actor to have its own Ability System Component, there are cases in which you might want an Actor, such as a player's Pawn or Character, to use an Ability System Component owned by another Actor, like a Player State or Player Controller. Reasons for this may include things like a player's score, or long-lasting ability cooldown timers that do not reset when the player's Pawn or Character is destroyed and respawned, or when the player possesses a new Pawn or Character. The Gameplay Ability System supports this behavior; to implement it, write the Actor's GetAbilitySystemComponent function so that it returns the Ability System Component you want to use. [Official Documentation](https://docs.unrealengine.com/5.0/en-US/gameplay-ability-system-component-and-gameplay-attributes-in-unreal-engine/)

## So, What does AbilitySystemComponent do in CommonGAS?
Our ASC is mainly handling the initialization for the ``CommonExtensionComponent`` and relationship of ``AbilityTagRelationshipMapping``.

C++ API:

Name                                  | Functionality
------------------------------------- | ------------------
GetActiveAbilitiesWithTags            | Returns a list of currently active ability instances that match the tags
GetAbilitySystemComponentFromActor    |  Version of function in AbilitySystemGlobals that returns correct type
AbilityInputTagPressed                |  
AbilityInputTagReleased               |  
ProcessAbilityInput                   |  
ClearAbilityInput                     |  
SetTagRelationshipMapping             |  Sets the current tag relationship mapping, if null it will clear it out
GetAdditionalActivationTagRequirements|  Looks at ability tags and gathers additional required and blocking tags

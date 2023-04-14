#API


## CommonGameplayAbility

** Class Defaults **

Map of gameplay tags to gameplay effect containers and Boolean check if an ability to be granted on granted

![Image](commongameplayabilityclassdefault.png)

Context                       | Config directory
----------------------------- | ------------------
Effect Container Map | An array of CommonEffectContainer reference
Activate Ability On Granted | Boolean


## OnGiveAbility
Called when the ability is given to an AbilitySystemComponent

![Image](ongiveability.png)

## OnRemoveAbility
Called when the ability is removed from an AbilitySystemComponent 

![Image](onremoveability.png)



## OnAvatarSet
If an ability is marked as 'ActivateAbilityOnGranted', activate them immediately when given here

![Image](onavatarset.png)

## CommonAbilitySystemComponent

## CommonAbilitySystemLibrary

GetActiveAbilitiesWithTags
Return a list of all active abilities with given ability tags container


Input

Ability Tags
Gameplay Tag Container


Output

Active Abilities
An array of CommonGameplayAbility 


GetCooldownRemainingTag
Returns total time and remaining time for cooldown tags. Returns false if no active cooldowns found

Input

Cooldown Tags
Gameplay Tag Container


Output

Time Remaining
Float
Cooldown Duration
Float
Return Value
Float


ActivateAbilitiesWithTags
Attempts to activate all abilities that match the specified tags
Returns true if it thinks it activated, but it may return false positives due to failure later in activation.
If bAllowRemoteActivation is true, it will remotely activate local/server abilities, if false it will only try to locally activate the ability




Input
Ability Tags
Gameplay Tag Container
Allow Remote Activation
Boolean


Output
Return Value
Boolean


GrantAbility
Grant a gameplay ability to owner Abilitysystemcomponent’s list of active abilities

Input

New Ability
Gameplay Ability class reference

RemoveAbility
Remove a gameplay ability from owner Abilitysystemcomponent’s list of active abilities

Input

Ability
Gameplay Ability class reference


DoesEffectContainerSpecHaveEffects

Input

Container Spec
CommonEffectContainerSpec reference

Output

Return Value
Boolean






ClearEffectContainerSpecTargets

Input

Container Spec
CommonEffectContainerSpec reference


DoesEffectContainerSpecHaveTargets

Input

Container Spec
CommonEffectContainerSpec reference

Output

Return Value
Boolean










AddTargetsToEffectContainerSpec

Input

Container Spec
CommonEffectContainerSpec reference
Hit Results
An array of hit result reference
Target Actors
An array of actor reference

Output

Return Value
CommonEffectContainerSpec 


ApplyExternalEffectContainerSpec

Input

Container Spec
CommonEffectContainerSpec reference

Output

Return Value
An array of ActiveGameplayEffectHandle reference




GameplayTasks
PlayMontageAndWaitForEvent

Input

Task Instance Name
FName
Montage To Play
UAnimMontage
Event Tags
GameplayTagContainer
Rate
Float
Start Section
FName
Stop when Ability Ends
Boolean
Anim Root Motion Translation Scale
Float








Output

Async Task


On Completed
 The montage completely finished playing 
On Blend Out
 The montage started blending out 
On Interrupted
The montage was interrupted 
On Cancelled
 The ability task was explicitly cancelled by another ability 
Event Received
 One of the triggering gameplay events happened 
Event Tags
GameplayTag
Event Data
GameplayEventData



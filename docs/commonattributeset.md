General UAttributeSet to be subclassed and provide Health and Mana functionality

 Things like Death and Respawn will not be handle in this attributeset

 ``Note``: In the future, if there's a demand for such system, i will be using this AttributeSet as a base for OnDeath and OnRespawn for Respawning character

 ``UAttributeSet``

 Explanation:

 ```
 Defines the set of all GameplayAttributes for your game Games should subclass this and add FGameplayAttributeData properties to represent attributes like health, damage, etc AttributeSets are added to the actors as subobjects, and then registered with the AbilitySystemComponent It often desired to have several sets per project that inherit from each other You could make a base health set, then have a player set that inherits from it and adds more attributes
 ```

 Gameplay Attributes | Functionality
---------------------| ------------------
Health               | By default, the value of is capped by 50.f
MaxHealth            | By default, the value of is capped by 100.f
Mana                 | By default, the value of is capped by 50.f
MaxMana              | By default, the value of is capped by 100.f
Damage               | This Damage is just used for applying negative health mods. Its not a 'persistent' attribute
Healing              | This Healing is just used for applying positive health mods. Its not a 'persistent' attribute
## GetActiveAbilitiesWithTags

Return a list of all active abilities with given ability tags container

![Image](img/getactiveabilitywithtags.png)

Name                          | Types
----------------------------- | ------------------
Ability Tags    (Input)       | Gameplay Tag Container
Active Abilities (Output)     | An array of CommonGameplayAbility 

## GetCooldownRemainingTag

Returns total time and remaining time for cooldown tags. Returns false if no active cooldowns found

![Image](img/getcooldownremainingfortag.png)

Name                          | Types
----------------------------- | ------------------
Cooldown Tags    (Input)      | Gameplay Tag Container
Time Remaining (Output)       | Float 
Cooldown Duration (Output)    | Float 
Return Value (Output)         | Boolean 

## ActivateAbilitiesWithTags
Attempts to activate all abilities that match the specified tags
Returns true if it thinks it activated, but it may return false positives due to failure later in activation.
If bAllowRemoteActivation is true, it will remotely activate local/server abilities, if false it will only try to locally activate the ability

![Image](img/activateabilitywithtags.png)

Name                                  | Types
--------------------------------------| ------------------
Ability Tags    (Input)               | Gameplay Tag Container
Allow Remote Activation (Input)       | Boolean 
Return Value (Output)                 | Boolean

## GrantAbility

Grant a gameplay ability to owner Abilitysystemcomponent’s list of active abilities


![Image](img/grantability.png)

Name                                  | Types
--------------------------------------| ------------------
New Ability    (Input)                | Gameplay Ability class reference

## RemoveAbility

Remove a gameplay ability from owner Abilitysystemcomponent’s list of active abilities


![Image](img/removeability.png)

Name                                  | Types
--------------------------------------| ------------------
Ability    (Input)                    | Gameplay Ability class reference

## DoesEffectContainerSpecHaveEffects

![Image](img/doeseffectcontainerspechaveeffects.png)

Name                                  | Types
--------------------------------------| ------------------
Container Spec    (Input)             | CommonEffectContainerSpec 
Return Value    (Output)              | Boolean

## ClearEffectContainerSpecTargets

![Image](img/cleareffectcontainerspectargets.png)

Name                                  | Types
--------------------------------------| ------------------
Container Spec    (Input)             | CommonEffectContainerSpec reference

## DoesEffectContainerSpecHaveTargets

![Image](img/doeseffectcontainerspechavetargets.png)

Name                                  | Types
--------------------------------------| ------------------
Container Spec    (Input)             | CommonEffectContainerSpec reference
Return Value    (Output)              | Boolean

## AddTargetsToEffectContainerSpec

![Image](img/addtargetstoeffectcontainerspec.png)

Name                                  | Types
--------------------------------------| ------------------
Container Spec    (Input)             | CommonEffectContainerSpec referenc
Hit Results    (Input)                | An array of hit result reference
Target Actors    (Input)              | An array of actor reference
Return Value    (Output)               | CommonEffectContainerSpec

## ApplyExternalEffectContainerSpec

![Image](img/applyexternaleffectcontainerspec.png)

Name                                  | Types
--------------------------------------| ------------------
Container Spec    (Input)             | CommonEffectContainerSpec reference
Return Value    (Output)              | An array of ActiveGameplayEffectHandle reference



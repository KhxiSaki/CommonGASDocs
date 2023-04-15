#Prerequisites
1. Enable the Gameplay Ability System Plugin in the Edit -> Plugins window.
![Image](img/GameplayAbilitySystem_Plugin_00.jpg)
2. To get the full range of capabilities of this system, add "GameplayAbilities", "GameplayTags", and "GameplayTasks" to PublicDependencyModuleNames in your project's "(ProjectName).Build.cs" file.

To use the Gameplay Ability System, add the three module names anywhere in the braced list, as follows: 
```
PublicDependencyModuleNames.AddRange(new string[] { "GameplayAbilities", "GameplayTags", "GameplayTasks" });
```
#Basic Setup

![type:video](https://www.youtube.com/embed/R66iJSezpEA)

1. Reparent your character class to CommonModularCharacter.h
2. Reparent your player controller class to CommonModularPlayerController.h
3. Reparent your player state class to CommonModularPlayerState.h
4. Reparent your game mode class to CommonModularGameMode.h

To see if you configured CommonGAS correctly, go to the command bar and use the following command:

 ``showdebug abilitysystem``

## Using Enhanced Input System 

From Unreal Engine 5.1 onwards, the EnhancedInput plugin will replace the legacy input system. If your project is from Unreal Engine 5.0 and below, make sure to enable the EnhancedInput Plugin by:

``Plugins->Input->EnhancedInput``

 - Find your blueprint character class and open it
 - Go to the Component Section and Add the CommonPlayerInputBindingComponent
 - Create Your InputActions for Keyboards controls such as MoveForward,MoveRight,LookUp,LookRight with Corresponding Axis Value and Bool Value
 - Input Mappings and Add Corresponding Bindings to Input Actions
 - Find CommonGAS ->PlayerControls category and configure your Mapping Context 

To see if you configure Enhanced Input correctly, go to the command bar and use the following command:

``showdebug enhancedinput``

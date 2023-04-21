The Game Features and Modular Gameplay plugins help developers create standalone features for their projects. Building features with these plugins offers several benefits, including keeping your project's codebase clean and readable, and avoiding accidental interactions or dependencies between unrelated features. This is particularly important when developing live products that change their feature sets over time. [Official Documentation](https://docs.unrealengine.com/5.1/en-US/game-features-and-modular-gameplay-in-unreal-engine/)

By default, there are four ``game features action`` available for you.

Name                          | Functionality
----------------------------- | ------------------
Add Cheats                    | Action extend the Cheat Manager, creating new "cheat codes" or extending existing ones. Cheat codes are helpful for debugging, and are    automatically removed from shipping builds. The ~ (tilde) key opens the console where you can enter these codes while running your project.
Add Components                | Actions take a list of Actor subclasses and add a set of Components to them on an opt-in basis. This is the most common way to use the Game Features and Modular Gameplay plugins, since Components are well-suited to encapsulating a wide range of behaviors.
Add Data Registry             | Actions add one or more Data Registries to the project. Data Registries are efficient places to store and retrieve globally-registered data.
Add Data Registry Source      | Actions add one or more Data Tables to existing Data 

In CommonGAS, we provided you GameFeatureAction for GameplayAbilitySystem taken from [ValleyOfTheAncientDemo](https://www.unrealengine.com/marketplace/en-US/product/ancient-game-01) and [LyraGameSample](https://www.unrealengine.com/marketplace/en-US/product/lyra)


Name                          | Functionality
----------------------------- | ------------------
Add Abilities                 | Add gameplay abilities and gameplay effects when enabled and remove gameplay abilities and gameplay effects when disabled
Add InputMappingContext       | Add an InputMappingContext when enabled and remove an InputMappingContext when disabled


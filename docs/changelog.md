## 1.1 (Unreal Engine 5.1.1)
- Fix visibility for some Decorators and Tasks
- Remove old exposes function inside CommonModMagnitudeCalculation

## 1.1.01 (Unreal Engine 5.1.1)
- Fix some leftover naming from previous code merge back in september 2022
- K2_OnPawnAvatarSet is not working due to not hook up to OnAvatarSet()
- Remove and backlog CommonAIPawn and CommonAIPawnWithStateTree
- Remove default values of attributes in CommonAttributeSet constructor. we prefer to do this either using infinite GameplayEffect or data table
- Remove GrantAbility in extension component. prefer using ASC one.
- Add new EGameplayEffectReplicationMode into DefaultCharacterData and PostInitiProperties() in CommonModularPawn,CommonModularActor,CommonModularCharacter
- Add new asset types for Common  classes and factory for custom CommonGAS category
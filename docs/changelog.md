## 1.1 (Unreal Engine 5.1.1)
- Fix visibility for some Decorators and Tasks (Bugfixes)
- Remove old exposes function inside CommonModMagnitudeCalculation (Bugfixes)

## 1.1.01 (Unreal Engine 5.1.1)
- Fix some leftover naming from previous code merge back in september 2022 (Bugfixes)
- K2_OnPawnAvatarSet is not working due to not hook up to OnAvatarSet() (Bugfixes)
- Remove and backlog CommonAIPawn and CommonAIPawnWithStateTree (Removed)
- Remove default values of attributes in CommonAttributeSet constructor. we prefer to do this either using infinite GameplayEffect or data table (Bugfixes)
- Remove GrantAbility in extension component. prefer using ASC one. (Removed)
- Add new EGameplayEffectReplicationMode and PostInitiProperties() in CommonModularPawn,CommonModularActor,CommonModularCharacter (New)
- Add Default Character Data (New)
- Add Input Mapping Data (New)
- Add CommonGASEditor Modules with new asset types for Common  classes and factory for custom CommonGAS category(New)
- Remove InputMappingContext and Input Priority from AbilityInputBindingComponent as this interaction being replaced by InputMappingData (Bugfixes)
- UAbilitySystemLibrary GameplayTags operation doesnt execute (bugfixes)
- Redo UGameplayCueFunction Library implemetations (Bugfixes)

## 1.1.02 (Unreal Engine 5.2.0)
- Fix undefined type 'USkeletalMeshComponent in CommonAbilitySystemComponent
- Fix 'AnimLayers': references must be initialized
- Fix use of undefined type 'FAnimMontageInstance'
- Clean up unused includes and forwards declarations
- Remove CommonInputComponent
- Fix use of undefined type 'APlayerController' in CommmonModularCharacter

Minimal class that supports extension by game feature plugins

This class is meant to be use with ``UCommonModularCharacter`` with ASC living in PlayerSate

## C++ API

Name                           | Functionality
-------------------------------| ------------------
GetCommonAbilitySystemComponent| Getter to get CommonAbilitySystemComponent


## AbilitySystemComponent

Type: ``UCommonAbilitySystemComponent``

## ReplicationMode

Type: ``EGameplayEffectReplicationMode``

Enabled : ``Mixed``

 How gameplay effects will be replicated to clients 

 Name                          | Functionality
-------------------------------| ------------------
Minimal                        | Only replicate minimal gameplay effect info. Note: this does not work for Owned AbilitySystemComponents (Use Mixed instead).
Mixed                          | Only replicate minimal gameplay effect info to simulated proxies but full info to owners and autonomous proxies
Full                           | Replicate full gameplay info to all


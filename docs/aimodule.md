In Common GAS, you can choose to either use ``StateTree`` or the standard ``AIModule`` when it comes to build an AI system.
I already provided you with some helpful ``Decorators``and ``Tasks`` if you using the standard AIModule but if you're using ``StateTree``, we dont provided any decorators and tasks as i havent battle tested StateTree enough but in the future, maybe i will provided some so you can still build your ai logic with ``StatetTree``

![Image](img/AIFolder.png)

In this example, im going to show you the basic setup to get you going.


## Setup

- By Default, CommonGAS already enabled ``AIModule`` ,``StateTree`` and ``GameplayStateTree`` if you're planning to use that plugin and added them as dependecies. 
![Image](img/statetree.png)

- For any AI-controlled characters, they need to inherit from ``CommonModularPawn`` and ``CommonAIPawnWithStateTree`` if you're planning to use StateTree

![Image](img/commonmodularpawn1.png)

![Image](img/commonmodularpawn2.png)

- Next, you need to make an ``AIController`` inherit from ``CommonModularAIController`` to control the AI.

![Image](img/aicontroller.png)

- In the blueprint graph, on ``BeginPlay`` we simply call the ``Run Behaviour Tree`` and apply your behaviour tree asset.
![Image](img/aicontroller_beginplay.png)

- Lastly, in your ``pawn`` class class default, find ``Pawn->Ai Controller Class`` and set your AIController to the one we created.

Now, thats the basic setup that should get you going. Have fun building your AIs!

## Tasks

In Common GAS, i have provided you with some useful ``Tasks`` you can use with GAS to build your gameplay logic:

# BTTask_ActivateAbilityByClass

![Image](img/BTTask_ActivateAbilityByClass.png)

![Image](img/BTTask_ActivateAbilityByClass1.png)

# BTTask_ActivateAbilityByTags

![Image](img/BTTask_ActivateAbilityByTags.png)

![Image](img/BTTask_ActivateAbilityByTags1.png)

# BTTask_ActivateAbilityOnce

![Image](img/BTTask_ActivateAbilityOnce.png)

![Image](img/BTTask_ActivateAbilityOnce1.png)

# BTTask_AddLooseGameplayTag

![Image](img/BTTask_AddLooseGameplayTag.png)

![Image](img/BTTask_AddLooseGameplayTag1.png)

# BTTask_AddLooseGameplayTags

![Image](img/BTTask_AddLooseGameplayTags.png)

![Image](img/BTTask_AddLooseGameplayTags1.png)

# BTTask_ApplyGameplayEffectToSelf

![Image](img/BTTask_ApplyGameplayEffectToSelf.png)

![Image](img/BTTask_ApplyGameplayEffectToSelf1.png)

# BTTask_ApplyGameplayEffectToTarget

![Image](img/BTTask_ApplyGameplayEffectToTarget.png)

![Image](img/BTTask_ApplyGameplayEffectToTarget1.png)

# BTTask_RemoveLoooseGameplayTags

![Image](img/BTTask_RemoveLoooseGameplayTags.png)

![Image](img/BTTask_RemoveLoooseGameplayTags1.png)

# BTTask_RemoveLooseGameplayTag

![Image](img/BTTask_RemoveLooseGameplayTag.png)

![Image](img/BTTask_RemoveLooseGameplayTag1.png)

# BTTask_SendGameplayEvent

![Image](img/BTTask_SendGameplayEvent.png)

![Image](img/BTTask_SendGameplayEvent1.png)

## Decorators

In Common GAS, i have provided you with some useful ``Decorators`` you can use with GAS to build your gameplay logic:

# BTDecorator_HasAllGameplayTags

![Image](img/BTDecorator_HasAllGameplayTags.png)

![Image](img/BTDecorator_HasAllGameplayTags1.png)

# BTDecorator_HasAnyMatchingGameplayTags

![Image](img/BTDecorator_HasAnyMatchingGameplayTags.png)

![Image](img/BTDecorator_HasAnyMatchingGameplayTags1.png)

# BTDecorator_HasMatchingGameplayTag

![Image](img/BTDecorator_HasMatchingGameplayTag.png)

![Image](img/BTDecorator_HasMatchingGameplayTag1.png)

# BTDecorator_IsAbilitySystemComponentValid

![Image](img/BTDecorator_IsAbilitySystemComponentValid.png)

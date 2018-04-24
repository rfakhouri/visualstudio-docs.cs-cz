---
title: 'CA1013: Přetižte operátor rovnosti společně s přetížením operátorů sčítání a odečítání'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
helpviewer_keywords:
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
ms.assetid: 5bd28d68-c179-49ff-af47-5250b8b18a10
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7fd43cc3077c037b70eaa8107563bd8f40b6a096
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1013-overload-operator-equals-on-overloading-add-and-subtract"></a>CA1013: Přetižte operátor rovnosti společně s přetížením operátorů sčítání a odečítání
|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverloadingAddAndSubtract|
|CheckId|CA1013|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Veřejný nebo chráněný typ implementuje operátory sčítání a odčítání, aniž by implementoval operátor rovnosti.

## <a name="rule-description"></a>Popis pravidla
 Pokud instance typu mohou být kombinovány s použitím operací, jako je například sčítání a odečítání, byste měli definovat téměř vždy rovnosti vrátil `true` pro jakékoli dvě instance, které mají stejné základní hodnoty.

 Operátor rovnosti výchozí nelze použít v přetížené implementace operátor rovnosti. To způsobí, že k přetečení zásobníku. Pokud chcete implementovat operátor rovnosti, použijte metodu Object.Equals v implementaci. Podívejte se na téma v následujícím příkladu.

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, implementujte operátor rovnosti, takže bude matematicky konzistentní s operátory sčítání a odečítání.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné při poskytuje výchozí implementaci operátor rovnosti správné chování pro daný typ potlačit upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V následujícím příkladu definuje typ (`BadAddableType`) porušil toto pravidlo. Tento typ měli implementovat operátor rovnosti Chcete-li jakékoli dvě instance, které mají stejné hodnoty polí testování `true` rovnosti. Typ `GoodAddableType` ukazuje opravené implementaci. Všimněte si, že tento typ také implementuje operátor nerovnosti a přepíše <xref:System.Object.Equals%2A> vyhovět ostatní pravidla. Dokončení implementace by také implementovat <xref:System.Object.GetHashCode%2A>.

 [!code-csharp[FxCop.Design.AddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_1.cs)]

## <a name="example"></a>Příklad
 Následující příklad testů pro porovnávání pomocí instance typy, které byly dříve definované v tomto tématu pro ilustraci výchozí a správné chování pro operátor rovnosti.

 [!code-csharp[FxCop.Design.TestAddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_2.cs)]

 Tento příklad vytvoří následující výstup.

 **Chybný typ: {2,2} {2,2} jsou stejné? Ne**
**dobrý typu: {3,3} {3,3} jsou stejné? Ano**
**dobrý typu: {3,3} {3,3} jsou ==?   Ano**
**chybný typ: {2,2} {9,9} jsou stejné? Ne**
**dobrý typu: {3,3} {9,9} jsou ==?   Ne**
## <a name="see-also"></a>Viz také
 [Operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators)
---
title: 'CA1402: Vyhněte se přetížení ve viditelných rozhraních modelu COM'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
helpviewer_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
ms.assetid: 2724c1f9-d5d3-4704-b124-21c4d398e5df
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: aa45a54a994d19b1a04bc0785f21b88dfeef4475
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922129"
---
# <a name="ca1402-avoid-overloads-in-com-visible-interfaces"></a>CA1402: Vyhněte se přetížení ve viditelných rozhraních modelu COM

|||
|-|-|
|TypeName|AvoidOverloadsInComVisibleInterfaces|
|CheckId|CA1402|
|Kategorie|Microsoft. interoperabilita|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Rozhraní, které je viditelné rozhraní modelu COM (Component Object Model), deklaruje přetížené metody.

## <a name="rule-description"></a>Popis pravidla
Když jsou přetížené metody vystaveny klientům modulu COM, zachová svůj název pouze první přetížení metody. Následná přetížení jsou jednoznačně přejmenována přidáním znaku podtržítka ' _ ' a celé číslo, které odpovídá pořadí deklarace přetížení. Zvažte například následující metody:

```csharp
void SomeMethod(int valueOne);
void SomeMethod(int valueOne, int valueTwo, int valueThree);
void SomeMethod(int valueOne, int valueTwo);
```

Tyto metody jsou zveřejněny pro klienty modelu COM, jak je uvedeno níže.

```csharp
void SomeMethod(int valueOne);
void SomeMethod_2(int valueOne, int valueTwo, int valueThree);
void SomeMethod_3(int valueOne, int valueTwo);
```

Klienti modelu COM Visual Basic 6 nemohou implementovat metody rozhraní pomocí podtržítka v názvu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, přejmenujte přetížené metody tak, aby názvy byly jedinečné. Alternativně můžete nastavit rozhraní jako neviditelné na modelu COM změnou dostupnosti `internal` na`Friend` ( [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]v) nebo použitím <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> atributu nastaveného na `false`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
Následující příklad ukazuje rozhraní, které porušuje pravidlo a rozhraní, které splňuje pravidlo.

[!code-vb[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/VisualBasic/ca1402-avoid-overloads-in-com-visible-interfaces_1.vb)]
[!code-csharp[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/CSharp/ca1402-avoid-overloads-in-com-visible-interfaces_1.cs)]

## <a name="related-rules"></a>Související pravidla
[CA1413: Vyhněte se neveřejným polím v viditelných hodnotových typech modelu COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

[CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

[CA1017: Označte sestavení pomocí ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Viz také:

- [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)
- [Datový typ Long](/dotnet/visual-basic/language-reference/data-types/long-data-type)
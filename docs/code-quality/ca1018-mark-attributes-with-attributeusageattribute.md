---
title: 'CA1018: Označte atributy pomocí AttributeUsageAttribute'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
helpviewer_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
ms.assetid: 6ab70ec0-220f-4880-af31-45067703133c
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: dfdaca64c166a29ad731719f79bbad57e975ff8b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043723"
---
# <a name="ca1018-mark-attributes-with-attributeusageattribute"></a>CA1018: Označte atributy pomocí AttributeUsageAttribute

|||
|-|-|
|TypeName|MarkAttributesWithAttributeUsage|
|CheckId|CA1018|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 <xref:System.AttributeUsageAttribute?displayProperty=fullName> Atribut není k dispozici pro vlastní atribut.

## <a name="rule-description"></a>Popis pravidla
 Při definování vlastního atributu jej označte použitím <xref:System.AttributeUsageAttribute> k označení, kde ve zdrojovém kódu vlastní atribut lze použít. Význam a zamýšlené použití atributu určuje jeho platné umístění v kódu. Můžete definovat atribut, který identifikuje uživatele, který zodpovídá za údržbu a vylepšování jednotlivé typy v knihovně, a zodpovědností je vždy přiřazené na úrovni typu. V takovém případě kompilátory by měly umožnit atributů na třídy, výčty a rozhraní, ale neměli byste ji povolit pro metody, události nebo vlastnosti. Organizační zásady a postupy by určovat, zda má být povolen atribut v sestavení.

 <xref:System.AttributeTargets?displayProperty=fullName> Výčet definuje cíle, které určíte pro vlastní atribut. Vynecháte-li <xref:System.AttributeUsageAttribute>, vlastní atribut bude platit pro všechny cíle, podle definice `All` hodnotu <xref:System.AttributeTargets> výčtu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zadejte cíle pro atribut s použitím <xref:System.AttributeUsageAttribute>. Podívejte se na téma v následujícím příkladu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Měli opravit porušení tohoto pravidla místo vyloučení zprávy. I v případě, že dědí atribut <xref:System.AttributeUsageAttribute>, atribut by měl být k dispozici pro zjednodušení údržby kódu.

## <a name="example"></a>Příklad
 Následující příklad definuje dva atributy. `BadCodeMaintainerAttribute` nesprávně vynechává <xref:System.AttributeUsageAttribute> příkaz, a `GoodCodeMaintainerAttribute` správně implementuje atributu, který je popsán výše v této části. Všimněte si, že vlastnost `DeveloperName` vyžaduje pravidlo návrhu [CA1019: Definujte přístupové objekty pro argumenty atributu](../code-quality/ca1019-define-accessors-for-attribute-arguments.md) a je zahrnuté pro úplnost.

 [!code-csharp[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/CSharp/ca1018-mark-attributes-with-attributeusageattribute_1.cs)]
 [!code-vb[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/VisualBasic/ca1018-mark-attributes-with-attributeusageattribute_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1019: Definujte přístupové objekty pro argumenty atributu](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)

 [CA1813: Vyhněte se nezapečetěným atributům](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>Viz také:

- [Atributy](/dotnet/standard/design-guidelines/attributes)
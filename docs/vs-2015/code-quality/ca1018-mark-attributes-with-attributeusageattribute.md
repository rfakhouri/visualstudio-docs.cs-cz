---
title: 'CA1018: Označte atributy pomocí AttributeUsageAttribute | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
helpviewer_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
ms.assetid: 6ab70ec0-220f-4880-af31-45067703133c
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a8b7cea6ea74b336c862cfe44f90e3e1ec54b2c2
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65704220"
---
# <a name="ca1018-mark-attributes-with-attributeusageattribute"></a>CA1018: Označte atributy pomocí AttributeUsageAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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

 [!code-csharp[FxCop.Design.AttributeUsage#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AttributeUsage/cs/FxCop.Design.AttributeUsage.cs#1)]
 [!code-vb[FxCop.Design.AttributeUsage#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AttributeUsage/vb/FxCop.Design.AttributeUsage.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1019: Definujte přístupové objekty pro argumenty atributu](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)

 [CA1813: Vyhněte se nezapečetěným atributům](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>Viz také
 [Atributy](https://msdn.microsoft.com/library/ee0038ef-b247-4747-a650-3c5c5cd58d8b)

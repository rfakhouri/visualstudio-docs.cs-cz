---
title: 'CA1813: Vyhněte se nezapečetěným atributům'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1813
- AvoidUnsealedAttributes
helpviewer_keywords:
- CA1813
- AvoidUnsealedAttributes
ms.assetid: f5e31b4c-9f8b-49e1-a2a8-bb5f1140729a
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b7b5b360a6288b6ff2e13b6d7fc29df6728fad6f
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546246"
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813: Vyhněte se nezapečetěným atributům

|||
|-|-|
|TypeName|AvoidUnsealedAttributes|
|CheckId|CA1813|
|Kategorie|Microsoft.Performance|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Veřejný typ dědí z <xref:System.Attribute?displayProperty=fullName>není abstraktní a není zapečetěná (`NotInheritable` v jazyce Visual Basic).

## <a name="rule-description"></a>Popis pravidla

[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Knihovny tříd poskytuje metody pro načítání vlastních atributů. Ve výchozím nastavení tyto metody prohledávají hierarchii dědičnosti atributů. Například <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> vyhledá zadaného typu atributu nebo libovolný typ atributu, který rozšiřuje zadaného typu atributu. Zapečetění atributu eliminuje prohledávání hierarchie dědičnosti a může zlepšit výkon.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, zapečeťte typ atributu nebo vytvořit abstraktní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla. Potlačit pouze v případě, že definujete hierarchii atributů a nelze zapečetit atribut nebo vytvořit abstraktní.

## <a name="example"></a>Příklad

Následující příklad ukazuje vlastní atribut, který splňuje toto pravidlo.

[!code-csharp[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/CSharp/ca1813-avoid-unsealed-attributes_1.cs)]
[!code-vb[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/VisualBasic/ca1813-avoid-unsealed-attributes_1.vb)]

## <a name="related-rules"></a>Související pravidla

- [CA1019: Definujte přístupové objekty pro argumenty atributu](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)
- [CA1018: Označte atributy pomocí AttributeUsageAttribute](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)

## <a name="see-also"></a>Viz také:

- [Atributy](/dotnet/standard/design-guidelines/attributes)
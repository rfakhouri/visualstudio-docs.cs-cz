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
ms.workload:
- multiple
ms.openlocfilehash: b861591355a47d38beec921a13643841b40e4465
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813: Vyhněte se nezapečetěným atributům
|||
|-|-|
|TypeName|AvoidUnsealedAttributes|
|CheckId|CA1813|
|Kategorie|Microsoft.Performance|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejné typ dědí od <xref:System.Attribute?displayProperty=fullName>, není abstraktní a není zapečetěná (`NotInheritable` v jazyce Visual Basic).

## <a name="rule-description"></a>Popis pravidla
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Knihovny tříd poskytuje metody pro získání vlastní atributy. Ve výchozím nastavení tyto metody vyhledávání hierarchie dědičnosti atribut; například <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> hledá zadaného typu atributu nebo kterýkoli typ atributu, který rozšiřuje zadaného typu atributu. Zapečetění atribut eliminuje hledání prostřednictvím hierarchie dědičnosti a může zlepšit výkon.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, zapečetit typ atributu nebo nastavit jej jako abstraktní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné upozornění toto pravidlo potlačit. Měli byste to provést pouze v případě, že jsou definice hierarchie atributů a nemůžete zapečetit atribut nebo nastavit jej jako abstraktní.

## <a name="example"></a>Příklad
 Následující příklad ukazuje vlastní atribut splňující toto pravidlo.

 [!code-csharp[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/CSharp/ca1813-avoid-unsealed-attributes_1.cs)]
 [!code-vb[FxCop.Performance.AttributesSealed#1](../code-quality/codesnippet/VisualBasic/ca1813-avoid-unsealed-attributes_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1019: Definujte přístupové objekty pro argumenty atributu](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)

 [CA1018: Označte atributy pomocí AttributeUsageAttribute](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)

## <a name="see-also"></a>Viz také
 [Atributy](/dotnet/standard/design-guidelines/attributes)
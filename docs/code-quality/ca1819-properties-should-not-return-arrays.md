---
title: 'CA1819: Vlastnosti by neměly vracet pole'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 68f64d37a7616f095a86452353edc498d2d27f28
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549414"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: Vlastnosti by neměly vracet pole

|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|Kategorie|Microsoft.Performance|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejné nebo chráněné vlastnosti veřejného typu vrací pole.

## <a name="rule-description"></a>Popis pravidla
 Pole vrácená vlastnostmi nejsou chráněna proti zápisu, i v případě, že vlastnost je jen pro čtení. Abyste pole ochránili před změnou, musí vlastnost vrátit kopii tohoto pole. Uživatelé obvykle nebudou rozumět nepříznivým výkonnostním důsledkům volání těchto vlastností. Konkrétně se může použít vlastnost jako indexovaná vlastnost.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, metodu nastavení vlastnosti nebo změňte vlastnost na vrácení kolekce.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Atributy mohou obsahovat vlastnosti, které vrací pole, ale nemůže obsahovat vlastnosti, které vracejí kolekce. Můžete potlačit upozornění, která se vyvolá pro vlastnost, která je odvozena z atributu <xref:System.Attribute> třídy. V opačném případě nepotlačujte upozornění tohoto pravidla.

## <a name="example-violation"></a>Příklad porušení

### <a name="description"></a>Popis
 Následující příklad ukazuje vlastnost, která poruší toto pravidlo.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

### <a name="comments"></a>Komentáře
 Chcete-li opravit porušení tohoto pravidla, metodu nastavení vlastnosti nebo změňte vlastnost na vrácení kolekce místo pole.

## <a name="change-the-property-to-a-method-example"></a>Změňte hodnotu vlastnosti na příkladu – metoda

### <a name="description"></a>Popis
 V následujícím příkladu řeší porušení změnou vlastnosti na metodu.

### <a name="code"></a>Kód
 [!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
 [!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

## <a name="return-a-collection-example"></a>Vrátí kolekci příklad

### <a name="description"></a>Popis
 V následujícím příkladu řeší porušení změnou vlastnosti se vraťte

 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allowing-users-to-modify-a-property"></a>Umožní uživatelům měnit vlastnosti

### <a name="description"></a>Popis
 Můžete chtít umožnit příjemci třídy k úpravě vlastností. Následující příklad ukazuje vlastnost pro čtení a zápis, který porušuje tato pravidla.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
 [!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

### <a name="comments"></a>Komentáře
 V následujícím příkladu řeší porušení změnou vlastnosti se vraťte <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>.

### <a name="code"></a>Kód
 [!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
 [!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)
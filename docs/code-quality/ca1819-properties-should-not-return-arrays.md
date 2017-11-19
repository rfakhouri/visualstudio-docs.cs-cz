---
title: "CA1819: Vlastnosti by neměly vracet pole | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2bd2aae360789646c78fa6b292b1ad97490fc2da
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: Vlastnosti by neměly vracet pole
|||  
|-|-|  
|TypeName|PropertiesShouldNotReturnArrays|  
|CheckId|CA1819|  
|Kategorie|Microsoft.Performance|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Vlastnost veřejných nebo chráněné v veřejného typu vrátí pole.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pole vrácené vlastnosti nejsou chráněna proti zápisu, i když vlastnost je jen pro čtení. Abyste pole ochránili před změnou, musí vlastnost vrátit kopii tohoto pole. Uživatelé obvykle nebudou rozumět nepříznivým výkonnostním důsledkům volání těchto vlastností. Konkrétně se může použít vlastnost jako indexované vlastnosti.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, byla vlastnost metoda nebo změnit vlastnost, která má vracet kolekci.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Atributy mohou obsahovat vlastnosti, které vracejí pole, ale nemůže obsahovat vlastnosti, které vracejí kolekce. Můžete potlačit upozornění, které se vyvolá pro atribut, který je odvozený od vlastnosti <xref:System.Attribute> třídy. Jinak není potlačení upozornění od tohoto pravidla.  
  
## <a name="example-violation"></a>Příklad porušení  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje vlastnosti, která porušuje toto pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]  
  
### <a name="comments"></a>Komentáře  
 Opravit porušení toto pravidlo, zkontrolujte vlastnost metodu nebo změňte vlastnost, která má vracet kolekci místo pole.  
  
## <a name="change-the-property-to-a-method-example"></a>Nastavte vlastnost na příkladu – metoda  
  
### <a name="description"></a>Popis  
 Následující příklad opraví porušení změnou vlastnosti na metodu.  
  
### <a name="code"></a>Kód  
 [!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
 [!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]  
  
## <a name="return-a-collection-example"></a>Vrátí kolekci příklad  
  
### <a name="description"></a>Popis  
 Následující příklad opraví porušení změnou vlastnosti vrátit  
  
 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]  
  
## <a name="allowing-users-to-modify-a-property"></a>Umožňuje uživatelům změnit vlastnost  
  
### <a name="description"></a>Popis  
 Můžete chtít povolit příjemce třídy, jestliže chcete upravit. Následující příklad ukazuje vlastnosti pro čtení a zápis, která porušuje toto pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
 [!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]  
  
### <a name="comments"></a>Komentáře  
 Následující příklad opraví porušení změnou vlastnosti vrátit <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>.  
  
### <a name="code"></a>Kód  
 [!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
 [!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)
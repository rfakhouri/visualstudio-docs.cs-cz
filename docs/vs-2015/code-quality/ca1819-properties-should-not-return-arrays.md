---
title: 'CA1819: Vlastnosti by neměly vracet pole | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f2f9c46b84da6cb25f04bb862bea8c4dcd81f968
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902061"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: Vlastnosti by neměly vracet pole
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1819: vlastnosti by neměly vracet pole](https://docs.microsoft.com/visualstudio/code-quality/ca1819-properties-should-not-return-arrays).

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
 Atributy mohou obsahovat vlastnosti, které vrací pole, ale nemůže obsahovat vlastnosti, které vracejí kolekce. Můžete potlačit upozornění, která se vyvolá pro vlastnost atributu, který je odvozen od třídy [System.Attribute] (<!-- TODO: review code entity reference <xref:assetId:///System.Attribute?qualifyHint=False&amp;autoUpgrade=True>  -->) třídy. V opačném případě nepotlačujte upozornění tohoto pravidla.

## <a name="example-violation"></a>Příklad porušení

### <a name="description"></a>Popis
 Následující příklad ukazuje vlastnost, která poruší toto pravidlo.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayViolation/cs/FxCop.Performance.PropertyArrayViolation.cs#1)]
 [!code-vb[FxCop.Performance.PropertyArrayViolation#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayViolation/vb/FxCop.Performance.PropertyArrayViolation.vb#1)]

### <a name="comments"></a>Komentáře
 Chcete-li opravit porušení tohoto pravidla, metodu nastavení vlastnosti nebo změňte vlastnost na vrácení kolekce místo pole.

## <a name="change-the-property-to-a-method-example"></a>Změňte hodnotu vlastnosti na příkladu – metoda

### <a name="description"></a>Popis
 V následujícím příkladu řeší porušení změnou vlastnosti na metodu.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayFixedMethod/cs/FxCop.Performance.PropertyArrayFixedMethod.cs#1)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayFixedMethod/vb/FxCop.Performance.PropertyArrayFixedMethod.vb#1)]

## <a name="return-a-collection-example"></a>Vrátí kolekci příklad

### <a name="description"></a>Popis
 V následujícím příkladu řeší porušení změnou vlastnosti se vraťte

 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayFixedCollection/cs/FxCop.Performance.PropertyArrayFixedCollection.cs#1)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayFixedCollection/vb/FxCop.Performance.PropertyArrayFixedCollection.vb#1)]

## <a name="allowing-users-to-modify-a-property"></a>Umožní uživatelům měnit vlastnosti

### <a name="description"></a>Popis
 Můžete chtít umožnit příjemci třídy k úpravě vlastností. Následující příklad ukazuje vlastnost pro čtení a zápis, který porušuje tato pravidla.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyModifyViolation/cs/FxCop.Performance.PropertyModifyViolation.cs#1)]
 [!code-vb[FxCop.Performance.PropertyModifyViolation#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyModifyViolation/vb/FxCop.Performance.PropertyModifyViolation.vb#1)]

### <a name="comments"></a>Komentáře
 V následujícím příkladu řeší porušení změnou vlastnosti se vraťte <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyModifyFixed/cs/FxCop.Performance.PropertyModifyFixed.cs#1)]
 [!code-vb[FxCop.Performance.PropertyModifyFixed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyModifyFixed/vb/FxCop.Performance.PropertyModifyFixed.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)




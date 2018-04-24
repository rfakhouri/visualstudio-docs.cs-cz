---
title: 'CA1044: Vlastnosti by neměly být pouze pro zápis'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PropertiesShouldNotBeWriteOnly
- CA1044
helpviewer_keywords:
- CA1044
- PropertiesShouldNotBeWriteOnly
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 204108ed86d37594d7debc0a69139a7f2a28a44a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1044-properties-should-not-be-write-only"></a>CA1044: Vlastnosti by neměly být pouze pro zápis
|||
|-|-|
|TypeName|PropertiesShouldNotBeWriteOnly|
|CheckId|CA1044|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Vlastnost veřejných nebo chráněného nemá přistupující objekt set, ale nemá přistupující objekt get.

## <a name="rule-description"></a>Popis pravidla
 Získat přístupové objekty poskytnout přístup pro čtení k vlastnosti a přístupových objektů sady zadejte oprávnění k zápisu. Ačkoli je přijatelné a často nezbytné použít vlastnost jen pro čtení, směrnice návrhu zakazují použití vlastností jen pro zápis. Je to proto, takže uživatel, nastavte hodnotu a pak bránit uživateli v zobrazení hodnota neposkytuje žádné zabezpečení. Taktéž bez přístupu pro čtení není možné zobrazit stav sdílených objektů, což omezuje jejich užitečnost.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, přidejte přistupující objekt get pro vlastnost. Případně pokud chování vlastnosti jen pro zápis je nutné, zvažte, převod této vlastnosti na metodu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Důrazně doporučujeme, aby není potlačit upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V následujícím příkladu `BadClassWithWriteOnlyProperty` je typ s vlastností jen pro zápis. `GoodClassWithReadWriteProperty` obsahuje kód opravené.

 [!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/VisualBasic/ca1044-properties-should-not-be-write-only_1.vb)]
 [!code-csharp[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/CSharp/ca1044-properties-should-not-be-write-only_1.cs)]
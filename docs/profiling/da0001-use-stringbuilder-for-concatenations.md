---
title: 'DA0001: Pro zřetězování používejte StringBuilder | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0001
- vs.performance.rules.DAUseStringBuilder
- vs.performance.1
- vs.performance.rules.DA0001
ms.assetid: a7cc7613-ad5f-48c8-bd2b-56372cc12dfc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 78b8e4d8b0a8ac7a2afbe0eb501ff496b3ade188
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="da0001-use-stringbuilder-for-concatenations"></a>DA0001: Pro zřetězování používejte StringBuilder
|||  
|-|-|  
|Id pravidla|DA0001|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování<br /><br /> Instrumentace|  
|Zpráva|Zvažte použití StringBuilder zřetězení řetězců|  
|Typ zprávy|Upozornění|  
  
## <a name="cause"></a>příčina  
 Volání System.String.Concat jsou podstatnou část data profilování. Zvažte použití <xref:System.Text.StringBuilder> třída k vytvoření řetězce z více segmentech.  
  
## <a name="rule-description"></a>Popis pravidla  
 A <xref:System.String> objekt se nedá změnit. Proto všechny změny řetězec vytvoří nový objekt řetězce a uvolňování původního. Toto chování je stejný, ať už výslovně volání String.Concat nebo pomocí operátory zřetězení řetězců, jako například + nebo +=... Pokud může dojít ke snížení výkonu programu tyto metody se často nazývají například když znaky jsou přidány na řetězec v úzkou smyčku.  
  
 Třídy StringBuilder je měnitelný objekt, a na rozdíl od System.String, většina metod na StringBuilder, které upravují instance této třídy vrátíte odkaz na stejnou instanci. Můžete vložit znaky nebo připojit k instanci StringBuilder, text a odebrat nebo nahrazení znaků v instanci bez nutnosti přidělování novou instanci a odstraňování původní instance.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Klikněte dvakrát na zprávy v okně Seznam chyb, přejděte na [zobrazení podrobností funkce](../profiling/function-details-view.md) odběru data profilu. Najít v částech programu, které využívají nejčastěji se vyskytující zřetězení řetězců. Pomocí třídy StringBuilder pro manipulace s řetězci komplexní, včetně operace sřetězení časté řetězec.  
  
 Další informace o tom, jak pracovat s řetězce [operace s řetězci](http://go.microsoft.com/fwlink/?LinkId=177816) části [kapitoly 5 - zlepšení výkonu kódu spravované](http://go.microsoft.com/fwlink/?LinkId=177817) v knihovně Microsoft Patterns and Practices.
---
title: "Postupy: Změna Namespace jazyka specifické pro doménu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, namespace
ms.assetid: f20c47e5-230d-4f0e-812f-5c6edb86866c
caps.latest.revision: "19"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: b7419766b4c195c3bcef2aa45e886004a89fb5ec
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Postupy: Změna oboru názvů jazyka specifického pro doménu
Obor názvů jazyka specifické pro doménu, můžete změnit. Je nutné provést změny v **DSL Explorer**, ve vlastnostech balíčku Dsl projektu a v informací o sestavení.  
  
### <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Chcete-li změnit obor názvů jazyka domény  
  
1.  V **DSL Explorer**, klikněte **Dsl** uzlu.  
  
2.  V **vlastnosti** změňte **Namespace** vlastnost.  
  
3.  Uložte řešení a transformace šablony.  
  
4.  Na **projektu** nabídky, klikněte na tlačítko **Dsl vlastnosti**.  
  
     Zobrazit vlastnosti pro váš projekt.  
  
5.  Klikněte **aplikace** kartě.  
  
6.  Změna **výchozí obor názvů** vlastnost na nový název oboru názvů.  
  
7.  Pokud chcete změnit název sestavení, změňte **vlastnost název sestavení.**  
  
8.  Pokud jste změnili název sestavení, otevřete DslPackage\Package.tt a aktualizovat tento řádek:  
  
     `string dslAssembly = "YourDSLassembly.Dsl.dll";`  
  
9. Pokud jste napsali libovolný vlastní kód, nezapomeňte změnit odkazy na obor názvů a třídy v souborech kódu.  
  
10. Resetovat Visual Studio experimentální instanci.  
  
    1.  Odstranit **\Users\\***{name}***\AppData\Local\Microsoft\VisualStudio\\\*Exp**  
  
    2.  V systému Windows **spustit** nabídce zvolte **všechny programy**, **Microsoft Visual Studio 2010 SDK**, **nástroje**, **resetovat Experimentální instanci**.  
  
11. Na **sestavení** nabídce zvolte **znovu sestavit řešení**.  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)
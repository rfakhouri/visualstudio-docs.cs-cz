---
title: "Postupy: Změna Namespace jazyka specifické pro doménu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, namespace
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 468cf24ccb16452c93583b2aa99af560d920bcf4
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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

[Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
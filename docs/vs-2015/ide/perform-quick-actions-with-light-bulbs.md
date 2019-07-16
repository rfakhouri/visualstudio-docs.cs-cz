---
title: Rychlé akce pomocí žárovek | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 990ee487-cf9a-4b89-9784-e7b47c220e8c
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 74237b42ebafb82e82705d42174efb6f6a4d3661
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68203722"
---
# <a name="perform-quick-actions-with-light-bulbs"></a>Rychlé akce pomocí žárovek
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ikony žárovky jsou novou funkcí produktivitu v sadě Visual Studio 2015. Jsou ikony, který se zobrazí v editoru sady Visual Studio a který můžete kliknout a rychlé akce včetně refaktoringu opravování chyb. Ikony žárovky přenést opravě chyby a často refaktoring pomoc do jediného bodu ústředním, klikněte pravým tlačítkem myši na řádek, ve kterém píšete.  
  
 ![Ikony žárovky malé](../ide/media/vs2015-lightbulbsmall.png "VS2015_LightBulbSmall")  
  
 V jazyce C# a Visual Basic zobrazí se žárovka, pokud existuje červená vlnovka a sady Visual Studio obsahuje návrh na tom, jak tento problém vyřešit. Například pokud máte chybu označená červenou vlnovkou, žárovka se zobrazí v případě opravy jsou k dispozici pro tuto chybu. V jazyce C++ při přidání nové funkce do souboru hlaviček, zobrazí se vám žárovky, která nabízí pro vytvoření zástupné procedury implementace této funkce. Pro libovolný jazyk třetím stranám poskytnete vlastní Diagnostika a návrhy, například jako součást sady SDK a sady Visual Studio návrhy se bylo možné podle těchto pravidel.  
  
## <a name="to-see-a-light-bulb"></a>Chcete-li zobrazit žárovky  
  
1. V mnoha případech se zobrazí návrhy samovolně při najetí myši v místě chybu nebo do levého okraje editoru při přesunutí blikající kurzor na řádek, který v něm došlo k chybě. Když se zobrazí červená vlnovka, myši a zobrazit žárovky. Může také způsobit žárovky má zobrazit, pokud používáte myš či klávesnice k přechodu na libovolné místo na řádku kde k problému dochází.  
  
2. Stisknutím klávesy **Ctrl +.** kdekoli v řádku pro vyvolání žárovky a přejít přímo na seznam potenciálních oprav.  
  
   ![Žárovka s najedete myší](../ide/media/vs2015-lightbulb-hover.png "VS2015_LightBulb_Hover")  
  
## <a name="to-see-potential-fixes"></a>Chcete-li zobrazit možné opravy  
 Klikněte na šipku dolů nebo zobrazit potenciál opravy odkaz zobrazíte seznam rychlé akce, které pro vás může trvat žárovky.  
  
 ![Žárovka rozšířit](../ide/media/vs2015-lightbulb-hover-expanded.png "VS2015_LightBulb_hover_expanded")  
  
## <a name="to-do-a-refactoring"></a>Provedete refaktoring  
 Refaktoring může stále zlepšovat kliknutím pravým tlačítkem na vyvolali místní nabídku, ale můžete také stisknout kombinaci kláves Ctrl +. Chcete-li zobrazit možnosti refaktorování. Na následujícím obrázku se refaktoring extrahovat metodu nabízí po stisknutí klávesy Ctrl +. někam na řádek, který obsahuje `Math.Abs` volání:  
  
 ![Žárovka zobrazující možnosti refaktorování](../ide/media/vs2015-lightbulbs-refactor.png "VS2015_LightBulbs_refactor")

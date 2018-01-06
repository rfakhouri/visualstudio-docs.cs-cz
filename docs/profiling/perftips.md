---
title: PerfTips | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 509d2d4f-48a5-4cdf-acad-6f7b75421303
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cfcb4fdf488233a2be7ea55b57d041641f2ea882
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="perftips"></a>PerfTips
Ladicí program Visual Studio *PerfTips* a integrovaná s ladicím programem **diagnostické nástroje** umožňují monitorovat a analyzovat výkon aplikace při ladění.  
  
 I když integrovaná s ladicím programem diagnostické nástroje jsou skvělý způsob od zjištění této problémy s výkonem při vývoji, ladicí program může mít významný dopad na výkon vaší aplikace. Ke shromažďování dat přesnější výkonu, zvažte použití nástroje Visual Studio diagnostiky, které spustit mimo ladicí program příliš jako další část vaší vyšetřování výkonu. V tématu [spuštění nástroje pro profilaci s nebo bez ladicího programu](../profiling/running-profiling-tools-with-or-without-the-debugger.md).  
  
## <a name="perftips"></a>PerfTips  
 Při zastavení ladicího programu provádění na zarážek nebo taktování operace, uplynulý čas mezi rozdělení a předchozí zarážek se jako tlačítka v okně editoru. Další informace najdete v tématu [PerfTips: informace o výkonu v přehledem při ladění pomocí sady Visual Studio](http://blogs.msdn.com/b/visualstudioalm/archive/2014/08/18/perftips-performance-information-at-a-glance-while-debugging-with-visual-studio.aspx).  
  
 ![PerfTip](../profiling/media/dbgdiag_perf_perftip.png "DBGDIAG_PERF_PerfTip")  
  
## <a name="diagnostics-tools-window"></a>Okno diagnostické nástroje  
 Zarážky a přidružené časových dat se zaznamenávají v okně diagnostické nástroje  
  
 Následující obrázek ukazuje okno diagnostické nástroje ve Visual Studiu 2015 Update 1:  
  
 ![DiagnosticTools & č. 45; Aktualizaci1](../profiling/media/diagnostictools-update1.png "DiagnosticTools aktualizaci1")  
  
-   **Rozdělit události** časová osa označit zarážky, které byly dosáhl v relaci ladění. Klikněte na událost, vyberte **ladicí program** podrobnosti seznamu.  
  
-   **Využití procesoru** graf ukazuje změnu ve využití procesoru mezi všechny jader procesoru v relaci ladění.  
  
-   **Události** seznam **ladicí program** podokno podrobností obsahovat položky pro všechny události pozastavení.  
  
-   **Doba trvání** sloupec události pozastavení Zobrazí uplynulý čas mezi událostí a předchozí zarážek.  
  
## <a name="turn-perftips-on-or-off"></a>PerfTips vypnutí a zapnutí  
 Pokud chcete povolit nebo zakázat PerfTips:  
  
1.  Na **ladění** nabídce zvolte **možnosti**.  
  
2.  Zaškrtněte nebo zrušte zaškrtnutí **Zobrazit uplynulý PerfTip při ladění**.  
  
## <a name="turn-the-diagnostic-tools-window-on-or-off"></a>Okno diagnostické nástroje vypnutí a zapnutí  
 Pokud chcete povolit nebo zakázat okno diagnostické nástroje:  
  
1.  Na **ladění** nabídce zvolte **možnosti**.  
  
2.  Zaškrtněte nebo zrušte zaškrtnutí **povolit diagnostické nástroje při ladění**.

## <a name="see-also"></a>Viz také
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)

---
title: Spuštění nástroje pro profilaci s nebo bez ladicího programu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 3fcdccad-c1bd-4c67-bcec-bf33a8fb5d63
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31ae64a24cab971ff54a92ec447371ad24bb7c24
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="running-profiling-tools-with-or-without-the-debugger"></a>Spuštění nástroje pro profilaci s nebo bez ladicí program
Visual Studio nyní nabízí možnost výkonu nástroje, z nichž některé (například **využití procesoru** a **využití paměti**) lze spustit s nebo bez něj. Nástroje pro sledování výkonu non-ladicí program slouží ke spuštění na verzi konfigurace, zatímco integrovaná s ladicím programem nástroje jsou určeny pro spuštění pro ladění konfigurace.  
  
## <a name="should-i-run-the-tool-with-or-without-the-debugger"></a>Měly být spuštěny s nebo bez ladicího programu nástroj?  
 Nástroje pro sledování výkonu integrovaná s ladicím programem umožňují dělat spoustu dalších věcí, které nelze nástroje ladicího programu, například nastavit zarážky a zkontrolujte hodnoty proměnné. Bez ladicí nástroje získáte prostředí, které bude co nejblíže ke co se zobrazí uživatelům vydané aplikace.  
  
 Tady je pár otázek, které vám pomohou rozhodnout, jaký druh nástroj je správný pro vaše záměry:  
  
1.  Problém najít aplikaci byl vyvinutý, nebo ji v byla nalezena vydanou verzi?  
  
     Pokud se problém, se kterým chcete pracovat s byl nalezen během vývoje, pravděpodobně nepotřebujete ke spuštění nástroje pro sledování výkonu v sestavení pro vydání. Pokud bylo zjištěno v prodejní verzi, doporučujeme reprodukujte problém s konfigurací verzi a potom se rozhodnete, zda by ladicí program Nápověda pro další šetření.  
  
2.  Zpracování potíže způsobené náročná na prostředky procesoru  
  
     Mnoho problémů jsou z důvodu problémů s výkonem externí například vstupně-výstupní nebo odezvy sítě, takže ho nesmí provést velký rozdíl, zda spustit nástroje pro sledování výkonu s nebo bez něj. Pokud je problém z důvodu volá náročná na prostředky procesoru, rozdíl mezi verze a ladění konfigurace může být výrazně a pravděpodobně by měla zkontrolovat, zda problém existuje v sestavení pro vydání před použitím nástroje integrovaná s ladicím programem  
  
3.  Potřebujete přesněji měření výkonu, nebo je přibližný počet přijatelné?  
  
     Ladění sestavení nedostatek určitých optimalizace, které poskytují sestavení pro vydání, například vložené volání funkcí a konstanty, vyřazení nepoužívané kód cesty a ukládání proměnné způsoby, které nelze použít pomocí ladicího programu. Ladicí program, samotné změní časy výkonu, protože vykonává určité operace, které jsou nezbytné pro ladění (například při zachycení výjimky a události modulu zatížení). Čísla výkon v nástrojích integrovaná s ladicím programem jsou méně přesné jako nespadá optimalizace ladicí program, ale stále může být užitečné při porovnání s další relativní měření pořízených při ladění. Jsou mnohem přesnější čísla výkonu pro verzi konfigurace pomocí nástrojů ladicí program.
  
##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a> Shromažďovat data profilování při ladění  
 Následující část se zabývá ladění místně. Můžete zjistit o ladění na zařízení nebo vzdálené ladění, v pozdějších částech.  
  
1.  Otevřete projekt, kterou chcete ladit, pak klikněte na tlačítko **ladění / spusťte ladění** (nebo **spustit** na panelu nástrojů nebo **F5**).  
  
2.  **Diagnostické nástroje** okno se automaticky zobrazí, pokud jste vypnuli ho. Zobrazte okno znovu, klikněte na tlačítko **ladění / Windows / zobrazit diagnostické nástroje**.  
  
3.  Spusťte scénáře, které chcete shromažďovat data.  
  
     Při spuštění relace, zobrazí se informace o události, proces paměť a využití CPU.  
  
     Následující grafické ukazuje **diagnostické nástroje** okno ve Visual Studiu 2015 Update 1:  
  
     ![DiagnosticTools&#45;Update1](../profiling/media/diagnostictools-update1.png "DiagnosticTools-Update1")  
  
4.  Můžete vybrat, jestli chcete zobrazit **využití paměti** nebo **využití procesoru** (nebo obě) s **vyberte nástroje** nastavení na panelu nástrojů. Pokud používáte Visual Studio Enterprise, můžete povolit nebo zakázat IntelliTrace v **nástroje / Možnosti / IntelliTrace**.  
  
5.  Relace diagnostiky skončí, když zastavíte ladění.  
  
 Ve Visual Studiu 2015 Update 1 **diagnostické nástroje** okno je jednodušší pro byste se zaměřit na události, které vás zajímají.   Názvy události se teď zobrazují s předponami kategorie (**gesto**, **výstup programu**, **zarážek**, **souboru** atd.), abyste mohli rychle Vyhledejte v seznamu pro danou kategorii nebo přeskočit kategorií, které vám nezáleží.  
  
 Okno teď má vyhledávací pole, aby mohli najít si konkrétní řetězec kdekoli v seznamu událostí. Následující obrázek zobrazuje výsledky hledání pro řetězec "instalaci" odpovídající čtyři události:  
  
 ![DiagnosticsEventSearch](../profiling/media/diagnosticseventsearch.png "DiagnosticsEventSearch")  
  
 Můžete také filtrovat události a deaktivovat zobrazení v okně. V **filtru** rozevíracího seznamu, můžete zkontrolovat nebo zrušte zaškrtnutí políčka určité kategorie události:. Názvy kategorií jsou stejné jako názvy předponu.  
  
 ![DiagnosticEventFilter](../profiling/media/diagnosticeventfilter.png "DiagnosticEventFilter")  
  
 Další informace najdete v tématu [hledání a filtrování kartě události v okně diagnostické nástroje](http://blogs.msdn.com/b/visualstudioalm/archive/2015/11/12/searching-and-filtering-the-events-tab-of-the-diagnostic-tools-window.aspx).  
  
## <a name="collect-profiling-data-without-debugging"></a>Shromažďovat data profilování bez ladění  
 Některé nástroje pro profilaci vyžadují oprávnění správce ke spuštění. Visual Studio můžete spustit jako správce, nebo můžete spustit jako správce nástrojů, při spuštění relace diagnostiky.  
  
1.  Otevřete projekt v sadě Visual Studio.  
  
2.  Na **ladění** nabídce zvolte **profileru výkonu...** (Klávesovou zkratku: Alt + F2).  
  
3.  Na stránce spuštění diagnostiky zvolte jeden nebo více nástroje ke spuštění v relaci. Zobrazí se pouze nástroje, které se vztahují na typu projektu, operační systém a programovací jazyk. Když zvolíte diagnostický nástroj, výběr nástroje, které nelze spustit ve stejné relaci diagnostiky jsou zakázány. Zde je, jak může vypadat vaše volby pro aplikace UWP C#:  
  
     ![Vyberte diagnostické nástroje](../profiling/media/diag_selecttool.png "DIAG_SelectTool")  
  
4.  Spuštění diagnostiky relace, klikněte na tlačítko **spustit**.  
  
5.  Spusťte scénáře, pro které chcete shromažďovat data.  
  
     Při spuštění relace, některé nástroje zobrazit grafy data v reálném čase na stránce spustit diagnostické nástroje.  
  
     ![Shromažďování dat na výkon a Diagnostika pag](../profiling/media/pdhub_collectdata.png "PDHUB_CollectData")  
  
6.  K ukončení relace diagnostiky, klikněte na tlačítko **zastavit shromažďování**.  
  
 Když zastavíte shromažďování dat v relaci diagnostiky, data se analyzují a sestava se zobrazí v stránky diagnostiky.  
  
 Můžete také otevřít relaci .diagnostic uložené soubory ze seznamu posledních otevřených na diagnostické nástroje spuštění stránky.  
  
 ![Otevřete soubor uložený diagnostiku relace](../profiling/media/pdhub_openexistingdiagsession.png "PDHUB_OpenExistingDiagSession")  
  
## <a name="the-profiling-report"></a>Sestavy pro profilaci  
 ![Diagnostika nástroje sestavy](../profiling/media/diag_report.png "DIAG_Report")  
  
|||  
|-|-|  
|![Krok 1](../profiling/media/procguid_1.png "ProcGuid_1")|Časová osa ukazuje délku relace profilace, aktivační události životního cyklu aplikace a uživatelské značky.|  
|![Krok 2](../profiling/media/procguid_2.png "ProcGuid_2")|Přetažením modrých panelů můžete vybrat určitou oblast časové osy a omezit tak sestavu jen na tuto část časové osy.|  
|![Krok 3](../profiling/media/procguid_3.png "ProcGuid_3")|Nástroj zobrazí jeden nebo více hlavní grafy. Pokud vaše relace diagnostiky je vytvořen s několik nástrojů, jsou zobrazeny všechny hlavní grafy.|  
|![Krok 4](../profiling/media/procguid_4.png "ProcGuid_4")|Můžete sbalit a rozbalit jednotlivé grafy.|  
|![Krok 5](../profiling/media/procguid_6.png "ProcGuid_6")|Pokud data zahrnují informace z několika nástrojů, podrobnosti pro tento nástroj se shromažďují na kartách.|  
|![Krok 6](../profiling/media/procguid_6a.png "ProcGuid_6a")|Nástroj může mít jeden nebo více zobrazení podrobností. Zobrazení je filtrovaná podle vybrané oblasti časové osy.|  
  
## <a name="setting-the-analysis-target-to-another-device"></a>Nastavení cílového analysis na jiné zařízení.  
 Kromě toho aplikace od projekt Visual Studio, můžete také spustit diagnostické relací na alternativní cíle. Například můžete chtít diagnostikovat problémy s výkonem na verzi vaší aplikace, která byla nainstalována z obchodu s aplikacemi Windows.  
  
 ![Vyberte cíl analysis diagnostické nástroje](../profiling/media/pdhub_chooseanalysistarget.png "PDHUB_ChooseAnalysisTarget")  
  
 Můžete spustit aplikace, které již jsou nainstalovány v zařízení nebo diagnostické nástroje můžete přiřadit některé aplikace, které jsou již spuštěny. Pokud vyberete **spuštění aplikace** nebo **nainstalované aplikace**, vyberte aplikaci ze seznamu, který zjistí aplikace v zadaném nasazení cíli.  
  
 ![Vyberte spuštěné nebo nainstalovanou aplikaci pro diagnostiku](../profiling/media/pdhub_selectrunningapp.png "PDHUB_SelectRunningApp")  
  
 Pokud vyberete **Internet Explorer**, zadejte adresu URL a můžete změnit cíl nasazení phone.  
  
 ![Zadejte adresu url pro zobrazení v aplikaci Internet Explorer](../profiling/media/pdhub_choosephoneanalysistarget.png "PDHUB_ChoosePhoneAnalysisTarget")  
  
## <a name="remote-debugging"></a>Vzdálené ladění  
 Relace diagnostiky systémem vzdáleného počítače nebo tabletu vyžaduje, aby vzdálené nástroje sady Visual Studio na vzdálený cíl nainstalovaná a spuštěná. Desktopové aplikace, najdete v části [vzdálené ladění](../debugger/remote-debugging.md).  Pro aplikace UWP, najdete v části [aplikace UWP spustit na vzdáleném počítači](../debugger/run-windows-store-apps-on-a-remote-machine.md).  
  
## <a name="blog-posts-and-msdn-articles-from-the-diagnostics-development-team"></a>Příspěvky blogu a články MSDN z vývojový tým diagnostiky  
 [Časopis MSDN: Analýza výkonu při ladění ve Visual Studiu 2015](https://msdn.microsoft.com/en-us/magazine/dn973013.aspx)  
  
 [Časopis MSDN: Pomůže rychleji diagnostikovat problémy IntelliTrace](https://msdn.microsoft.com/en-us/magazine/dn973014.aspx)  
  
 [Příspěvek blogu: diagnostikování nevracení obslužných rutin událostí pomocí nástroje využití paměti v sadě Visual Studio 2015](http://blogs.msdn.com/b/visualstudioalm/archive/2015/04/29/diagnosing-event-handler-leaks-with-the-memory-usage-tool-in-visual-studio-2015.aspx)  
  
 [Video: Historické ladění pomocí technologie IntelliTrace v sadě Microsoft Visual Studio Ultimate 2015](https://channel9.msdn.com/Events/Ignite/2015/BRK3716)  
  
 [Video: Ladění problémů s výkonem pomocí sady Visual Studio 2015](https://channel9.msdn.com/Events/Build/2015/3-731)  
  
 [PerfTips: Informace o výkonu na přehled při ladění pomocí sady Visual Studio](http://blogs.msdn.com/b/visualstudioalm/archive/2014/08/18/perftips-performance-information-at-a-glance-while-debugging-with-visual-studio.aspx)  
  
 [Diagnostické nástroje ladicí program oken v sadě Visual Studio 2015](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/diagnostic-tools-debugger-window-in-visual-studio-2015.aspx)  
  
 [IntelliTrace v sadě Visual Studio Enterprise 2015](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/intellitrace-in-visual-studio-ultimate-2015.aspx)

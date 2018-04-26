---
title: Tipy a triky v ladicím programu sady Visual Studio
description: Další tipy pro vyšší produktivitu v ladicím programu sady Visual Studio
ms.custom: ''
ms.date: 06/15/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 5262d8b1-2648-429e-85d5-90fcaadfb362
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bb4fb2c32f74a764e092e0e6f65685a358d64f54
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="learn-productivity-tips-and-tricks-for-the-debugger-in-visual-studio"></a>Další Rady a tipy pro vyšší produktivitu v ladicím programu sady Visual Studio

Přečtěte si toto téma další pár Rady a tipy pro vyšší produktivitu v ladicím programu sady Visual Studio. Podívejte se na základní funkce ladicího programu, najdete v části [prohlídka funkce ladicího programu](../debugger/debugger-feature-tour.md). V tomto tématu se týkají jsme některé oblasti, které nejsou součástí prohlídka funkce.

## <a name="pin-data-tips"></a>PIN kód datových tipech

Pokud je často ukazatel myši nad datových tipech při ladění, můžete připnout data tip pro proměnnou, abyste měli rychlý přístup. Proměnná zůstává definovaného i po restartování počítače. Připnutí data tip, klikněte na ikonu kódu pin při mohou přesouváním ukazatele myši nad ním. Budete moct připnout více proměnných.

![Připnutí Data Tip](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

## <a name="edit-your-code-and-continue-debugging-c-vb-c"></a>Kódu upravit a pokračovat, ladění (C#, VB, C++)

Ve většině jazyků – podpora Visual Studio můžete upravovat kód uprostřed ladicí relace a pokračovat, ladění. Chcete-li tuto funkci použít, klikněte na tlačítko do kódu s ukazatelem při pozastavena ladicí program, zkontrolujte úpravy a stiskněte klávesu **F5**, **F10**, nebo **F11** Chcete-li pokračovat, ladění.

![Upravit a pokračovat, ladění](../debugger/media/dbg-tips-edit-and-continue.gif "EditAndContinue")

Další informace o používání funkce a na omezení funkcí najdete v tématu [upravit a pokračovat](../debugger/edit-and-continue.md).

## <a name="debug-issues-that-are-hard-to-reproduce"></a>Ladění problémů, které se těžko Reprodukujte

Pokud je obtížné nebo znovu vytvořit konkrétní stav ve vaší aplikaci časově náročné, zvažte, ať už může pomoct použití podmíněné zarážky. Můžete použít [podmíněné zarážky](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) a filtrování zarážky pro vyhnout rozdělení do kódu aplikace, dokud aplikace vstupuje do požadovaného stavu (například stavu, ve kterém je proměnné ukládání chybná data). Můžete nastavit podmínky pomocí výrazů, filtrů, počtu položek a tak dále.

#### <a name="to-create-a-conditional-breakpoint"></a>Chcete-li vytvořit podmíněné zarážky

1. Klikněte pravým tlačítkem na ikonu zarážek (red míč) a zvolte **podmínky**.

2. V **nastavení zarážek** okno, zadejte na výrazu.

    ![Podmíněné zarážky](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

3. Pokud vás zajímá jiný typ podmínky, vyberte **filtru** místo **podmíněným výrazem** v **nastavení zarážek** dialogové okno a potom postupujte podle kroků Tipy pro filtr.

## <a name="change-the-execution-flow"></a>Tok provádění změn

S ladicím programem pozastavena na řádek kódu, pomocí myši můžete získat ukazatele žlutá šipka na levé straně. Přesuňte ukazatel žlutá šipka do jiného bodu v cestě provádění kódu. Pak pomocí F5 nebo příkaz krok spouštět aplikace.

![Přesuňte ukazatel provádění](../debugger/media/dbg-tour-move-the-execution-pointer.gif "přesunout ukazatel provádění")

Změnou toku provádění můžete provést akce, jako je testovací cesty provádění různých kódu nebo znova spustí kód bez restartování ladicího programu.

> [!WARNING]
> Často budete muset pečlivě s touto funkcí a zobrazí upozornění v popisu tlačítka. Příliš se může zobrazit další upozornění. Přesunutí kurzoru nelze vrátit vaší aplikace do předchozího stavu aplikace.

## <a name="track-an-out-of-scope-object-c-visual-basic"></a>Sledování objekt mimo rozsah (C#, Visual Basic)

Lze snadno zobrazit pomocí ladicího programu jako proměnné **sledovat** okno. Když však proměnné přejde mimo obor v **sledovat** okno, můžete si všimnout, že je šedě. V některých scénářích aplikace může změnit hodnotu proměnné i, když je proměnná mimo obor, a můžete chtít něj dávat pozor (například proměnné může dojít k uvolnění z paměti). Můžete sledovat proměnné tak, že vytvoříte pro něj v ID objektu **sledovat** okno.

#### <a name="to-create-an-object-id"></a>Chcete-li vytvořit ID objektu

1.  Nastavte zarážky téměř proměnné, která chcete sledovat.

2.  Spuštění ladicího programu (**F5**) a zastavení u zarážky.

3. Najít proměnné v **místní hodnoty –** okno (**ladění > Windows > místní hodnoty –**), klikněte pravým tlačítkem na proměnnou a vyberte **Zkontrolujte ID objektu**.

    ![Vytvoření ID objektu](../debugger/media/dbg-tips-watch-create-object-id.png "CreateObjectID")
  
4.  Měli byste vidět **$** plus číslo **místní hodnoty –** okno. Tato proměnná je ID objektu.
  
5.  Klikněte pravým tlačítkem na proměnná ID objektu a zvolte **Přidat kukátko**.

Další informace najdete v tématu [vytvořit ID objektu](../debugger/watch-and-quickwatch-windows.md#bkmk_objectIds).

## <a name="view-return-values-for-functions"></a>Zobrazení návratové hodnoty pro funkce

Chcete-li zobrazit návratové hodnoty pro funkce, podívejte se na funkce, které se zobrazují v **automobily** okno při krokování kódu jazyka. Návratovou hodnotu pro funkci zobrazíte Ujistěte se, že funkce, které vás zajímají již provedena (stiskněte **F10** jednou, pokud jsou nyní zastaveny při volání funkce). Zavření okna, je-li použít **ladění > Windows > automobily** otevřete **automobily** okno.

![Automatické hodnoty – okno](../debugger/media/dbg-tips-autos-window.png "AutosWindow")

Kromě toho můžete zadat funkcí v **Immediate** okno zobrazení návratové hodnoty. (Otevřete ho pomocí **ladění > Windows > Immediate**.)

![Příkazové podokno](../debugger/media/dbg-tips-immediate-window.png "ImmediateWindow")

Můžete také použít [pseudovariables](../debugger/pseudovariables.md) v **sledovat** a **Immediate** okno, jako například `$ReturnValue`.

## <a name="string_visualizer"></a>Zkontrolovat řetězce v vizualizéru

Při práci s řetězci, může být užitečné, chcete-li zobrazit celý formátovaný řetězec. Chcete-li zobrazit prostý text, XML, HTML nebo JSON řetězec, klikněte na ikonu lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "vizualizér ikonu") při ukazatele myši na proměnné obsahující hodnotu řetězce.

![Otevřete Vizualizéru řetězce](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

Vizualizér řetězce můžete zjistit, jestli je poškozený, v závislosti na typu řetězec na řetězec. Například prázdný **hodnotu** pole určuje podle typu vizualizér nebyl rozpoznán řetězec. Další informace najdete v tématu [dialogové okno vizualizér řetězce](../debugger/string-visualizer-dialog-box.md).

![Vizualizér řetězce JSON](../debugger/media/dbg-tips-string-visualizer-json.png "JSONStringVisualizer")

Pro několik jiné typy například WPF objekty, které se zobrazují v ladicího programu můžete také otevřít vizualizérech.

## <a name="break-into-code-on-handled-exceptions"></a>Rozdělit na kód na zpracovávaný výjimky

Ladicí program dělí do kódu na neošetřených výjimek. Však zpracovává výjimky (například výjimky, které se vyskytují `try/catch` bloku) může být také příčinu chyby a chcete prozkoumat, kdy k nim dojde. Ladicí program na přerušení do kódu pro zpracovávaný výjimky také tak, že nakonfigurujete možnosti v můžete nakonfigurovat **nastavení výjimky** dialogové okno. Dialogové okno otevřít tak, že zvolíte **ladění > Windows > Nastavení výjimky**.

**Nastavení výjimky** dialogové okno umožňuje zjistit ladicí program na přerušení do kódu na konkrétních výjimek. Na následující ilustraci ladicího programu dělí do vašeho kódu vždy, když `System.NullReferenceException` dojde. Další informace najdete v tématu [Správa výjimek](../debugger/managing-exceptions-with-the-debugger.md).

![Dialogové okno nastavení výjimky](../debugger/media/dbg-tips-exception-settings.png "ExceptionSettingsDialogBox")

## <a name="debug-deadlocks-and-race-conditions"></a>Ladění blokování a konflikty časování

Pokud potřebujete k ladění druhy problémů, které jsou společné pro vícevláknové aplikace, často pomáhá zobrazíte umístění vláken při ladění. To provedete pomocí snadno **zobrazit vláken ve zdroji** tlačítko.

#### <a name="to-show-threads-in-your-source-code"></a>Chcete-li zobrazit vláken ve zdrojovém kódu

1.  Při ladění, klikněte **zobrazit vláken ve zdroji** tlačítko ![zobrazit vláken ve zdroji](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker") v **ladění** panelu nástrojů.
  
2.  Podívejte se na oddělovací mezery na levé straně okna. Na tomto řádku, uvidíte *vlákno značky* ikonu ![vlákno značky](../debugger/media/dbg-thread-marker.png "ThreadMarker") , která se podobá dvěma vlákny hadříkem. Vlákno značky označuje, že vlákno je zastavená v tomto umístění.

    Všimněte si, že vlákno značku může částečně zakryté podle zarážky.
  
3.  Umístění ukazatele myši značky přístup z více vláken. Zobrazí se popis dat. Popis dat poznáte, název a vlákno identifikační číslo pro každé zastavené vlákno.

    Můžete také zobrazit umístění vláken v [okna paralelní zásobníky](../debugger/get-started-debugging-multithreaded-apps.md).

## <a name="examine-payloads-for-web-services-and-network-resources-uwp"></a>Zkontrolujte datových částí pro webové služby a síťovým prostředkům (UWP)

V aplikacích pro UPW, můžete analyzovat síťových operací provést pomocí `Windows.Web.Http` rozhraní API. Tento nástroj můžete pomáhají ladit webové služby a síťovým prostředkům. Chcete-li použít nástroj, vyberte **ladění > výkonu profileru**. Vyberte **sítě**a potom zvolte **spustit**. V aplikaci, projít scénář, který používá `Windows.Web.Http`a potom zvolte **zastavit shromažďování** pro generování sestavy.

![Profilace nástroj využívání sítě](../profiling/media/prof-tour-network-usage.png "NetworkUsageProfTool")

Vyberte operaci v souhrnné zobrazení na Zobrazit další podrobnosti.

![Podrobné informace v nástroji využití sítě](../profiling/media/prof-tour-network-usage-details.png "DetailedViewNetworkUsage")

Další informace najdete v tématu [využití sítě](../profiling/network-usage.md).

## <a name="get-more-familiar-with-how-the-debugger-attaches-to-your-app"></a>Seznamte se více s jak ladicí program připojí k vaší aplikace

Připojit k aplikaci spuštěné, načte ladicí program vygenerovaných přesný sestavení pro stejnou aplikaci, kterou se pokoušíte ladění souborů symbolu (.pdb). V některých případech může být užitečné trochu znalosti soubory symbolů. Můžete zkontrolovat, jak Visual Studio načte symbol soubory pomocí **moduly** okno.

Otevřete **moduly** okno při ladění výběrem **ladění > Windows > moduly**. **Moduly** okno s dotazem, jaké moduly ladicího programu je práce jako s uživatelského kódu, nebo [ *vlastní kód*](../debugger/just-my-code.md)a symbol načítání stavu pro modul. Ve většině scénářů ladicí program automaticky vyhledá soubory symbolů pro uživatelský kód, ale pokud chcete krok do (nebo ladění) kód rozhraní .NET framework, systému kód nebo kód třetí strany knihovny, jsou zapotřebí další kroky pro získat soubory správné symbolů.

![Zobrazení informací o symbolu v okně moduly](../debugger/media/dbg-tips-modules-window.png "ViewSymbolInformation")

Můžete načíst informací o symbolu přímo z **moduly** okna tak, že kliknete pravým tlačítkem a vyberete **načíst symboly**.

V některých případech Vývojáři aplikací dodávat aplikace bez odpovídající symbol soubory (redukuje), ale zachovat kopii odpovídající symbol soubory sestavení tak, aby se později ladění vydaná verze.

Jak ladicího programu klasifikuje kód jako uživatelský kód, najdete v tématu [pouze můj kód](../debugger/just-my-code.md). Další informace o soubory symbolů, najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů v ladicím programu sady Visual Studio](specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).

## <a name="learn-more"></a>Víc se uč

Další tipy a triky a podrobnější informace najdete v tématu tyto příspěvky blogu:

- [7 menší známé špionážní programy pro ladění v sadě Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/2017/06/26/7-lesser-known-hacks-for-debugging-in-visual-studio/)
- [7 skrytá gems v sadě Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/2017/10/05/7-hidden-gems-in-visual-studio-2017/)

## <a name="see-also"></a>Viz také
[Klávesové zkratky](../ide/tips-and-tricks-for-visual-studio.md)

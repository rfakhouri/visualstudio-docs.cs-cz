---
title: "Přechod na relaci ladění v sadě Visual Studio (Xaml a C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 1da33203-333f-4a05-b4e2-8d407c497233
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: d5fa005273ada8869da467c9db97e0263f43f555
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="navigate-a-debugging-session-in-visual-studio-xaml-and-c"></a>Přechod na relaci ladění ve Visual Studiu (Xaml a C#)
Tento úvodní ukazuje, jak se orientovat ladicí relace sady Visual Studio a postup zobrazení a změna stavu programu v relaci.  
  
 Tento rychlý start je pro vývojáře, kteří jsou nové ladění pomocí sady Visual Studio a pro vývojáře, kteří chtějí získat další informace o navigace v sadě Visual Studio ladění relace. Neposkytuje obrázky o ladění sám sebe. Metody v ukázkový kód slouží pouze k předvedení ladění postupů popsaných v tomto tématu. Metody nepoužívají osvědčené postupy při návrhu aplikace nebo funkce. Ve skutečnosti se rychle zjistit, že metody a aplikace, není udělat nic většinu vůbec.  
  
 Části této úvodní byly navrženy tak, aby jako nezávislé nejmenší, můžete přeskočit všechny oddíl, který obsahuje informace, které jste již obeznámeni s. Také se není nutné k vytvoření ukázkové aplikace; ale doporučujeme ho a provedli proces co největší.  
  
 **Ladicí program klávesové zkratky.** Navigace ladicí program Visual Studio je optimalizovaná pro myši a klávesnice. Řada kroků v tomto tématu zahrnout klávesové zkratky nebo klávesovou zkratku shod Poznámka. Například (klávesové: F5) označuje zadáním klávesu F5, spustí nebo pokračuje v provádění ladicího programu.  
  
## <a name="in-this-topic"></a>V tomto tématu  
 Další postup:  
  
-   [Vytvoření ukázkové aplikace](#BKMK_CreateTheApplication)  
  
-   [Nastavit a spustit, aby se bod přerušení, krokování s vnořením metodu a zkontrolujte dat programu](#BKMK_StepInto)  
  
-   [Do, přes, a to z metody](#BKMK_StepIntoOverOut)  
  
-   [Nastavení podmíněné zarážky, spustit na pozici kurzoru a vizualizovat proměnné](#BKMK_ConditionCursorVisualize)  
  
-   [Upravit a pokračovat, zotavit výjimku](#BKMK_EditContinueRecoverExceptions)  
  
##  <a name="BKMK_CreateTheApplication"></a>Vytvoření ukázkové aplikace  
 Ladění je o kódu, takže ukázková aplikace používá rozhraní aplikace pro UPW jenom pro účely vytvoření zdrojový soubor, ve kterém uvidíte navigace na relaci ladění jak funguje a jak zkontrolovat a změnit stav programu. Všechny kód, který bude vyvolán je volána z konstruktoru hlavní stránky. žádné události jsou zpracovávány a nebudou přidány žádné ovládací prvky.  
  
 **Vytvořte aplikaci pro UPW C# výchozí.** Otevřete Visual Studio. Na domovské stránce vyberte **nový projekt** odkaz. V dialogovém okně Nový projekt zvolte **Visual C#** v **nainstalovaná** seznamu a potom zvolte **univerzální pro Windows**. V seznamu šablon projektu, zvolte **prázdná aplikace (univerzální pro Windows)**. Visual Studio vytvoří nové řešení a projektu a zobrazí MainPage.xaml designer a editor kódu XAML.  
  
 **Otevření zdrojového souboru MainPage.xaml.cs.** Klikněte pravým tlačítkem na libovolné místo v editoru XAML a zvolte **kód zobrazení**. Zobrazí se souboru MainPage.xaml.cs kódu. Všimněte si, že pouze jednu metodu `MainPage()` konstruktoru, je uvedena v souboru.  
  
 **Konstruktor MainPage nahraďte ukázkový kód.** Delete – metoda MainPage(). Na tento odkaz: [ladicího programu navigační ukázkový kód (Xaml a C#)](https://github.com/MicrosoftDocs/visualstudio-docs/raw/master/docs/debugger/samples/debugger-navigation-sample-code-xaml-and-csharp.cs)a poté zkopírujte kód uvedené v části C# do schránky. (Vyberte **zpět** v prohlížeči nebo programu help viewer se vraťte do této stránce Rychlý start.) V editoru Visual Studio vložte kód v `partial class MainPage` bloku. Vyberte kombinace kláves CTRL + s k uložení souboru.  
  
 Nyní můžete provést spolu s příklady v tomto tématu.  
  
##  <a name="BKMK_StepInto"></a>Nastavit a spustit, aby se bod přerušení, krokování s vnořením metodu a zkontrolujte dat programu  
 Nejběžnější způsobem, že můžete začít relaci ladění je zvolte **spustit ladění** z **ladění** nabídky (klávesové: F5). Provádění začne a pokračuje až do dosažení zarážku, ručně pozastavení provádění, dojde k výjimce, nebo ukončení aplikace.  
  
 Při spuštění je pozastavená v ladicím programu, můžete zobrazit hodnotu active proměnné v data tip podržením ukazatele myši nad proměnnou. Můžete také otevřít okna lokální a automobily zobrazíte seznam active proměnné a jejich aktuální hodnoty. Přidání jedné nebo více proměnných kukátko – okno vám umožní soustředit na hodnotě proměnné jako aplikace pokračuje v provádění.  
  
 Po pozastavení provádění aplikace (označovaný také rozdělení do ladicího programu), můžete k řízení způsobu, jakým se spustí zbytek kódu programu. Můžete pokračovat řádek po řádku přechod z volání metody metodě samostatně, nebo zavolat metodu můžete provést v jediném kroku. Tyto postupy se nazývají procházení aplikace. Můžete také obnovit standardní provádění spuštěné na další zarážku, který jste nastavili, nebo na řádek, kde je umístěn kurzor aplikace. Můžete zastavit relaci ladění kdykoli. Ladicí program je určen k provedení nezbytných operací čištění a ukončení provádění.  
  
### <a name="example-1"></a>Příklad 1  
 V tomto příkladu zarážku v konstruktoru MainPage souboru MainPage.xaml.cs, krok do první metodu, zobrazit hodnoty proměnné a pak ukončete ladění.  
  
 **Nastavte zarážky.** Nastavte zarážky v příkaz `methodTrack = "Main Page";` v konstruktoru MainPage. Vyberte řádek v šedou barvou oddělovací mezery u editoru zdrojového kódu (klávesové: Umístěte kurzor na řádku a vyberte klíč F9).  
  
 ![Krokovat s vnořením](../debugger/media/dbg_basics_stepinto.png "DBG_Basics_StepInto")  
  
 Ikona zarážek se zobrazí v mřížky.  
  
 **Spusťte na zarážku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: F5).  
  
 Zahájí provádění a pozastaví spuštění bezprostředně před příkaz, ve kterém je nastavena zarážka aplikace. Ikonu aktuální řádek v mřížky identifikuje vaši polohu a zvýrazní aktuální příkaz.  
  
 ![Nastavit zarážky](../debugger/media/dbg_basics_setbreakpoint.png "DBG_Basics_SetBreakpoint")  
  
 Jsou nyní v ovládacím prvku spuštění aplikace a zkontrolovat stav programu, v průběhu příkazy programu.  
  
 **Krok do metody.** Na **ladění** nabídce zvolte **Krokovat s vnořením** (klávesové: F11).  
  
 ![Aktuálního řádku](../debugger/media/dbg_basics_currentline.png "DBG_Basics_CurrentLine")  
  
 Všimněte si, že ladicí program přesune na další řádek, který je volání metody test1. Zvolte Krokovat s vnořením znovu. Ladicí program přesune do vstupní bod test1 metody. To označuje, že byl načten metody v zásobníku volání a paměti pro místní proměnné byly přiděleny.  
  
 Když je krok do řádek kódu, ladicí program provede jeden z následujících akcí:  
  
-   Další příkaz není volání funkce ve vašem řešení, ladicí program spustí dotaz, přesune na další příkaz a potom pozastaví spuštění.  
  
-   Pokud příkaz volání funkce ve vašem řešení, přesune do vstupní bod volaná funkce ladicího programu a potom pozastaví spuštění.  
  
 Nadále krok do příkazy test1, dokud jste dosáhli místo přechodu. Ladicí program označuje pravé složené závorce složené metody.  
  
 **Zkontrolujte hodnoty proměnných v datových tipech.** Po přesunutí ukazatele myši nad název proměnné, se zobrazí název, hodnotu a typ proměnné v data tip.  
  
 ![Ladicí program data tip](../debugger/media/dbg_basics_datatip.png "DBG_Basics_DataTip")  
  
 Najeďte myší proměnnou `a`. Všimněte si, zadejte název, hodnotu a data. Najeďte myší proměnnou `methodTrack`. Znovu Všimněte si, zadejte název, hodnotu a data.  
  
 **Zkontrolujte hodnoty proměnných v místní hodnoty – okno.** Na **ladění** nabídky, přejděte na příkaz **Windows**a potom zvolte **místní hodnoty –**. (Klávesové: Alt + 4).  
  
 ![Místní hodnoty – okno](../debugger/media/dbg_basics_localswindow.png "DBG_Basics_LocalsWindow")  
  
 Místní hodnoty – windows je stromové zobrazení parametry a proměnné funkce. Vlastnosti objektové proměnné jsou podřízené uzly samotného objektu. `this` Proměnná je skrytý parametr metodě každý objekt, který představuje samotného objektu. V takovém případě představuje MainPage třídy. Protože `methodTrack` je členem MainPage typu třídy, jeho hodnota a data jsou uvedeny v řádku pod `this`. Rozbalte `this` uzel k zobrazení `methodTrack` informace.  
  
 **Přidáte sledování pro proměnnou methodTrack.** `methodWatch` Proměnná se používá v rámci této úvodní k zobrazení metody volat v příkladech. Aby bylo snazší zobrazíte hodnotu proměnné, přidejte ji do okna sledování. Klikněte pravým tlačítkem na název proměnné v místní hodnoty – okno a potom zvolte **Přidat kukátko**.  
  
 ![Kukátko – okno](../debugger/media/dbg_basics_watchwindow.png "DBG_Basics_WatchWindow")  
  
 Můžete sledovat několika proměnných v okně Sledování. Hodnoty proměnných sledovaných, jako jsou hodnoty v místních položek a dat tip windows, jsou aktualizovány při každém spuštění je pozastaveno. Proměnné můžete také přidat do okna kukátka z editoru kódu. Vyberte proměnné, které chcete sledovat, klikněte pravým tlačítkem a potom zvolte **Přidat kukátko**.  
  
##  <a name="BKMK_StepIntoOverOut"></a>Do, přes, a to z metody  
 Na rozdíl od zanoříte se do metodu s názvem metodou nadřazeného, provede metodu podřízené krokování přes metodu a pak pozastaví spuštění v metodě volání jako nadřazený obnoví. Může krok přes metodu, když se seznámíte se způsobem metoda funguje a si jisti, že jeho spuštění nebude mít vliv na problém, kterou zkoumáte.  
  
 Krokování s přes řádek kódu, který neobsahuje volání metody provede řádku stejně jako zanoříte se do řádku.  
  
 Krokování s mimo metodu podřízené pokračuje v provádění metody a pak pozastaví spuštění po vrátí metoda jeho volání metody. Může vystoupení ze dlouho funkce, když jste zjistili, že zbytek funkce není důležité.  
  
 Krokování s přes i krokování s mimo funkci spustit funkci.  
  
 ![Krok do, přes a mimo metody](../debugger/media/dbg_basics_stepintooverout.png "DBG_Basics_StepIntoOverOut")  
  
### <a name="example-2"></a>Příklad 2  
 V tomto příkladu krok do, přes a mimo metody.  
  
 **Volejte metodu priklad2 v konstruktoru MainPage.** Upravit konstruktor MainPage a nahraďte tento řádek `methodTrack = String.Empty;` s `Example2();`.  
  
 ![Volání metody priklad2 z metody ukázku](../debugger/media/dbg_basics_callexample2.png "DBG_Basics_CallExample2")  
  
 **Spusťte na zarážku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: F5). Ladicí program pozastaví spuštění u zarážky.  
  
 **Krok přes řádek kódu.** Na **ladění** nabídce zvolte **Krokovat s přeskočením** (klávesnice: F10). Ladicí program provede `methodTrack = "MainPage";` příkaz stejným způsobem jako zanoříte se do příkazu.  
  
 **Krokování s vnořením priklad2 a Example2_A.** Vyberte klíč F11 pro krok do metodu příklad 2. Přejděte ke kroku do priklad2 příkazy, dokud se nedostanete na řádku `int x = Example2_A();`. Opakujte krok do tohoto řádku přesunout do vstupní bod Example2_A. Krok do každý příkaz Example2_A, dokud se nevrátíte do priklad2 i nadále.  
  
 ![Priklad2](../debugger/media/dbg_basics_example2.png "DBG_Basics_Example2")  
  
 **Krok přes funkci.** Všimněte si, že na další řádek v test2, `int y = Example2_A();` je v podstatě stejný jako předchozí řádek. Můžete bezpečně přeskočit tento řádek. Vyberte klíč F10 pro přesun z opětném priklad2 do druhé volání Example2_A. Zvolte F10 a krok prostřednictvím této metody. Všimněte si, že `methodTrack` řetězec označuje metodu Example2_A byla spuštěna dvakrát. Také si všimněte, že ladicí program okamžitě přesune na další řádek. Nepozastaví provádění v bodu priklad2 obnoví.  
  
 **Krok mimo funkci.** Vyberte klíč F11 pro krok do Example2_B metoda. Všimněte si, že není příliš neliší od Example2_A Example2_B. Chcete-li krok mimo metodu, zvolte **Krokovat s Vystoupením** na **ladění** nabídky (klávesnice: Shift + F11). Všimněte si, že `methodTrack` proměnná Určuje, že byl proveden Example2_B a že ladicího programu vrátila do bodu, kde priklad2 obnoví.  
  
 **Zastavte ladění.** V nabídce ladění vyberte Zastavte ladění (klávesové: Shift + F5). Tím končí relaci ladění.  
  
##  <a name="BKMK_ConditionCursorVisualize"></a>Nastavení podmíněné zarážky, spustit na pozici kurzoru a vizualizovat proměnné  
 Podmíněné zarážky Určuje podmínku, která způsobí, že ladicí program na pozastavení provádění. Podmínka je zadaný libovolný kód výraz, který může být vyhodnocen jako true nebo false. Můžete například použít podmíněné zarážky pro zjištění stavu program v často zavolat metodu jenom v případě, že proměnné dosáhne určitou hodnotu.  
  
 Jako nastavení jednorázové zarážek je spuštěná na pozici kurzoru. Při spouštění je pozastaveno, můžete vybrat řádek ve zdroji a pokračovat v provádění dokud nebude dosaženo vybraný řádek. Například je může krokování smyčku v metodě a určit, že kód ve smyčce pracuje správně. Místo procházení každé iteraci smyčky, můžete spustit na kurzor, který je umístěn po provedení smyčky.  
  
 V některých případech je obtížné zobrazit hodnotu proměnné v řádku dat tip nebo proměnné okna. Ladicí program, můžete zobrazit v vizualizér text, který představuje formátovaný zobrazení na hodnoty v posuvného okna řetězců, HTML a Xml.  
  
### <a name="example-3"></a>Příklad 3  
 V tomto příkladu nastavíte podmíněné zarážky k přerušení na konkrétní iteraci smyčky a potom spusťte pro kurzor, který je umístěn za smyčky. Hodnota proměnné se také zobrazit v vizualizéru text.  
  
 **Volejte metodu Example3 v konstruktoru MainPage.** Upravit konstruktor MainPage a nahraďte tento řádek `methodTrack = String.Empty;` řádek `Example3();`.  
  
 ![Volání Example3 z metody ukázku](../debugger/media/dbg_basics_callexample3.png "DBG_Basics_CallExample3")  
  
 **Spusťte na zarážku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: F5). Ladicí program pozastaví spuštění v zarážka v metodě MainPage.  
  
 **Krokování s vnořením metodu Example3.** Zvolte **Krokovat s vnořením** na **ladění** nabídky (klávesové: F11) přesunout do vstupní bod Example3 metody. Krokování do metodu, dokud nebude mít vstupní jedno nebo dvě smyčky z pokračovat `for` bloku. Všimněte si, že ho by vám neměl zabrat dlouhou dobu projděte všechny 1000 iterací.  
  
 **Nastavení podmíněné zarážky.** V levém oddělovací mezery u okno kódu, klikněte pravým tlačítkem na řádku `x += i;` a potom zvolte **podmínku**. Vyberte **podmínku** zaškrtněte políčko a potom zadejte `i == 500;` v textovém poli. Vyberte **platí** možnost a zvolte **OK**. Zarážce umožňuje zkontrolujte hodnotu v 500th iterace `for` smyčky.  
  
 ![Dialogové okno Podmínka zarážek](../debugger/media/dbg_basics_breakpointcondition.png "DBG_Basics_BreakpointCondition")  
  
 Ikona podmíněného zarážek lze určit podle jeho bílé mezi.  
  
 ![Podmíněné zarážky](../debugger/media/dbg_basics_conditionalbreakpoint.png "DBG_Basics_ConditionalBreakpoint")  
  
 **Spusťte na zarážku.** V nabídce ladění zvolte pokračovat (klávesové: F5). V okně místní hodnoty – potvrďte, že aktuální hodnota `i` je 500. Všimněte si, že proměnná `s` je reprezentován jako jeden řádek a je mnohem delší než okno.  
  
 **Visual proměnnou string.** Klikněte na ikonu lupy v **hodnotu** sloupec `s`.  
  
 Zobrazí se okno vizualizér Text a hodnota řetězce, který se zobrazí jako řetězec s více řádky.  
  
 **Spusťte na pozici kurzoru.** Klikněte pravým tlačítkem myši na řádku `methodTrack += "->Example3";` a potom zvolte **spustit ke kurzoru** (klávesové: Přesuňte kurzor na řádek; CTRL + F10). Ladicí program dokončí iterace smyčky a potom na řádku pozastaví spuštění.  
  
 **Zastavte ladění.** V nabídce ladění vyberte Zastavte ladění (klávesové: Shift + F5). Tím končí relaci ladění.  
  
##  <a name="BKMK_EditContinueRecoverExceptions"></a>Upravit a pokračovat, zotavit výjimku  
 V některých případech když rozdělit na kód v ladicím programu sady Visual Studio máte možnost změnit hodnotu proměnných a to i logics příkazů. Tato funkce je volána upravit a pokračovat.  
  
 Upravit a pokračovat může být obzvláště užitečný při přerušení na výjimku. Místo nutnosti zastavte a znovu spusťte ladění dlouhé a související se situací postup vyhnout výjimku, můžete "unwind" výjimka přesunout provádění do bodu bezprostředně před k výjimce došlo a potom změnit problematické proměnnou nebo příkaz a v aktuální relaci ladění pokračujte ve stavu, který nevyvolá výjimku.  
  
 I když můžete použití operace upravit a pokračovat v celé řadě situacích, konkrétní podmínky, které nejsou podporují upravit a pokračovat se obtížné určit, protože podmínky, závisí na programovací jazyk, aktuální stav programu zásobníku a schopnost ladicího programu změnit stav bez poškozování proces. Nejlepší způsob, jak zjistit, jestli se podporuje o změnu upravit je právě vyzkoušet. ladicí program umožňuje okamžitě vědět, pokud změna není podporována.  
  
### <a name="example-4"></a>Příklad 4  
 V tomto příkladu spustit ladicí program na výjimku, rewind – výjimka, opravte logiku metody a potom změňte hodnotu proměnné, aby mohl pokračovat provedení metody.  
  
 **Volejte metodu Example4 v konstruktoru MainPage.** Upravit konstruktor MainPage() a nahraďte tento řádek `methodTrack = String.Empty;` řádek `Example4();`.  
  
 ![Volání Example4 z metody ukázku](../debugger/media/dbg_basics_callexample4.png "DBG_Basics_CallExample4")  
  
 **Spusťte na výjimku.** Spusťte relaci ladění výběrem **spustit ladění** na **ladění** nabídky (klávesové: F5). Stisknutím klávesy F5 pokračovat v provádění. Ladicí program pozastaví spuštění v výjimka v metodě Example4 a zobrazí se dialogové okno výjimka.  
  
 ![Výjimky – dialogové](../debugger/media/dbg_basics_exceptiondlg.png "DBG_Basics_ExceptionDlg")  
  
 **Změňte program logiku.** Je zřejmé, že je chybu v `if` podmínku: hodnota `x` by mělo být změněno při `x` rovná 0; není při `x` není rovna hodnotě nula. Zvolte **rozdělit** opravit logiku metody. Při pokusu upravit řádek, zobrazí se dialogové okno jiné.  
  
 ![Upravit a pokračovat – dialogové](../debugger/media/dbg_basics_editandcontinuedlg.png "DBG_Basics_EditAndContinueDlg")  
  
 Zvolte **upravit** a potom změňte řádek `if (x != 0)` k `if (x == 0)`. Ladicí program trvá změny program logiku ke zdrojovému souboru.  
  
 **Změňte hodnotu proměnné.** Zkontrolujte hodnotu `x` v tip dat nebo v místní hodnoty – okno. Stále je 0 (nula). Pokud se pokusíte provést příkaz, který způsobil výjimku původní, ji budou pouze throw znovu. Můžete změnit hodnotu `x`. V místní hodnoty – okno, dvakrát klikněte **hodnotu** sloupec **x** řádek. Změňte hodnotu od 0 do 1.  
  
 ![Úprava hodnoty v místní hodnoty – okno](../debugger/media/dbg_basics_editandcontinuefix.png "DBG_Basics_EditAndContinueFix")  
  
 Vyberte klíč F11 pro krok do příkaz, který dříve došlo k výjimce. Všimněte si, že provede řádku bez chyby. Zvolte F11 znovu.  
  
 **Zastavte ladění.** Na **ladění** nabídce zvolte **Zastavte ladění** (klávesové: Shift + F5). Tím končí relaci ladění.  
  
## <a name="see-also"></a>Viz také  
 [Spusťte relaci ladění (jazyka Visual Basic, C#, C++ a XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)   
 [Aktivovat pozastavení, obnovení a událostí na pozadí pro aplikace UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)   
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)
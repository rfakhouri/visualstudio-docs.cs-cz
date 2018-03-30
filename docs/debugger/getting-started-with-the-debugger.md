---
title: Další informace k ladění – Visual Studio | Microsoft Docs
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data
ms.custom: mvc
ms.date: 03/16/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: tutorial
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
caps.latest.revision: 1
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ad1c3264f7f7b0c13d8df099ab14288141ef4e6e
ms.sourcegitcommit: 064f8678f4a918e1dce60285090a9803d37dc34b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/30/2018
---
# <a name="learn-to-debug-using-visual-studio"></a>Další informace k ladění pomocí sady Visual Studio

Toto téma představuje funkce podrobný návod v ladicím programu sady Visual Studio. Pokud chcete vyšší úrovně zobrazení funkce ladicího programu, najdete v části [prohlídka funkce ladicího programu](../debugger/debugger-feature-tour.md).

Můžete buď si přečíst podél zobrazíte funkce ladicího programu nebo můžete stáhnout kompletní příklad používá v prohlídka funkce a podle kroků. Chcete-li stáhnout vzorek a podle nich zorientujete, přejděte na [ukázku Prohlížeč fotografií](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a).

|         |         |
|---------|---------|
|  ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video")  |    [Přehrát video,](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171) ladění, který ukazuje podobným způsobem. |

I když ukázkovou aplikaci C#, funkce se vztahuje na C++, Visual Basic, JavaScript a dalších jazyků – podpora Visual Studio (Pokud není uvedeno jinak).

V tomto kurzu provedete následující:

> [!div class="checklist"]
> * Spuštění ladicího programu a stiskněte tlačítko zarážky.
> * Další příkazy, které krok prostřednictvím kódu v ladicím programu
> * Zkontrolujte proměnné v datových tipech a ladicího programu
> * Prozkoumat zásobník volání
> * Použití pomocníka výjimka

## <a name="start-the-debugger"></a>Spuštění ladicího programu!

1. Chcete-li sledovat tyto kroky v sadě Visual Studio, stáhněte ukázku [na této stránce](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a).

    > [!IMPORTANT]
    > Potřebujete instalaci sady Visual Studio .NET – vývoj plochy zatížení spustit aplikaci, kterou používáme v ukázku.

2. Rozbalte projekt.

3. Otevřete Visual Studio a vyberte **soubor > Otevřít** nabídky příkaz, a potom vyberte **projekt nebo řešení**a potom otevřete složku, kam jste stáhli projektu.

     ![Otevřete ukázkový projekt](../debugger/media/dbg-tour-open-project.png "otevřeného projektu")

3. Otevřete ukázku Prohlížeč fotografií WPF > C# složky, vyberte soubor, photoapp.sln a vyberte **otevřete**.

     Projekt se otevře v sadě Visual Studio. Průzkumník řešení v pravém podokně se zobrazí všechny soubory projektu.

    ![Soubory Průzkumníka řešení](../debugger/media/dbg-tour-solution-explorer.png "Průzkumníku řešení")

4. Stisknutím klávesy F5 (**ladění > Spustit ladění** nebo **spustit ladění** tlačítko ![spustit ladění](../debugger/media/dbg-tour-start-debugging.png "spustit ladění") na panelu nástrojů ladění).

     ![Aplikace prohlížeče fotografií](../debugger/media/dbg-tour-wpf-app.png "fotografii prohlížeč aplikace")

     F5 začíná ladicího programu připojit k procesu aplikací, ale vpravo teď nemůžeme nebyly přidány žádné zarážky nebo provést žádné zvláštní prozkoumat kód aplikace. Proto aplikace právě načte a zobrazí fotografie bitové kopie.

     V této ukázky jsme budete trvat bližší pohled na této aplikaci pomocí ladicího programu a získat pohled na ladicího programu funkce.

5. Zastavení ladicího programu stisknutím kombinace kláves pro zastavení red ![Zastavte ladění](../debugger/media/dbg-tour-stop-debugging.png "Zastavte ladění") tlačítko.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Nastavit zarážky a spuštění ladicího programu

Chcete-li ladit, spusťte aplikaci pomocí ladicího programu připojit k procesu aplikací.

1. V `MainWindow` konstruktor MainWindow.xaml.cs, zarážku kliknutím na levém okraji první řádek kódu.

     ![Nastavit zarážky](../debugger/media/dbg-tour-set-a-breakpoint.gif "SetABreakPoint")

6. Stisknutím klávesy F5 nebo **spustit ladění** tlačítko spustí aplikaci, a ladicí program spustí na řádek kódu, kde nastavit bod přerušení.

    Žlutý šipku představuje příkaz na kterém pozastavena ladicí program, který také pozastaví spuštění aplikace na stejném místě (Tento příkaz ještě spuštěna).

    F5 pokračuje v kterém aplikace běží na další zarážku. (Pokud ještě není aplikace spuštěna, F5 spuštění ladicího programu a zastaví u první zarážky.)

    Zarážky jsou užitečné funkce, když víte, řádek kódu nebo části kódu, který chcete prozkoumat podrobně.

## <a name="restart-your-app-quickly"></a>Restartujte aplikace rychle

Klikněte **restartujte** ![restartujte aplikace](../debugger/media/dbg-tour-restart.png "RestartApp") tlačítka na panelu nástrojů Debug (Ctrl + Shift + F5).

Po stisknutí klávesy **restartujte**, ho šetří čas a zastavení aplikace a restartování ladicího programu. Ladicí program se pozastaví u první zarážky, který je dosáhl spuštěním kódu.

Ladicí program zastaví znovu u zarážky v nastavíte `MainWindow` konstruktor.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>Přejděte kódu v ladicím programu pomocí příkazů krok

Většinou, klávesové zkratky tady používáme, protože je dobrý způsob, jak získat rychlého při spuštění aplikace v ladicím programu (ekvivalentní příkazy jako nabídky příkazy se zobrazují v závorkách).

1. Stisknutím klávesy F11 (**ladění > Krokovat s vnořením**) na dvakrát zálohy provádění aplikaci `InitializeComponent()` funkce.

     ![Pomocí kroku do kódu F11](../debugger/media/dbg-tour-f11.png "F11 Krokovat s vnořením")

     Je F11 **Krokovat s vnořením** příkazů a přejde jeden příkaz spuštění aplikace v čase. F11 je dobrý způsob, jak prozkoumat toku provádění většiny podrobně. (Pokud chcete přesunout rychlejší prostřednictvím kódu, jsme ukážeme některé další možnosti také.) Ve výchozím nastavení, přeskočí ladicího programu přes jiný uživatelský kód (Pokud chcete další podrobnosti, projděte si téma [pouze můj kód](../debugger/just-my-code.md)).

     >[!NOTE]
     > Ve spravovaném kódu zobrazí se dialogové okno s dotazem, zda chcete být upozorněni, když automaticky krok přes vlastnosti a operátory (výchozí nastavení). Pokud chcete změnit nastavení později, zakažte **krok přes vlastnosti a operátory** nastavení v **nástroje > Možnosti** nabídky v části **ladění**.

2. Stiskněte klávesu F10 (**ladění > Krokovat s přeskočením**) několikrát, dokud nebude ladicí program zastaví na první řádek kódu `OnApplicationStartup` obslužné rutiny události.

     ![Krokovat s přeskočením kódu pomocí F10](../debugger/media/dbg-tour-f10-step-over.png "F10 Krokovat s přeskočením")

     F10 Posune ladění bez zanoříte se do funkce nebo metody v kódu aplikace (kód stále provádí). Stisknutím kombinace kláves F10 na `InitializeComponent` volání metody (namísto F11), jsme přeskočil kód implementace pro `InitializeComponent` (který možná jsme nejsou nyní zajímá).

## <a name="step-into-a-property"></a>Krok do vlastnosti

1. S ladicím programem pozastaveno na tomto řádku kódu:

    ````
    mainWindow.Photos.Path = Environment.CurrentDirectory + "\\images";
    ````

    Klikněte pravým tlačítkem na řádek kódu a vyberte **krok do konkrétní**, pak **SDKSamples.ImageSample.PhotoCollection.Path.set**

     ![Pomocí kroku do konkrétní funkce](../debugger/media/dbg-tour-step-into-specific.png "krok do konkrétní")

    Jak už bylo zmíněno dříve, ve výchozím nastavení ladicího programu přeskočí přes spravované vlastnosti a pole, ale **krok do konkrétní** příkaz umožňuje toto chování potlačit. Prozatím se chceme vypadat, co se stane, když `Path.set` vlastnost setter spustí. **Krok do konkrétní** získá nám `Path.set` sem kód.

     ![výsledek krokování s vnořením konkrétní](../debugger/media/dbg-tour-step-into-specific-2.png "krok do konkrétní")

     `Update` Metody v tomto kódu vypadá to, může to být zajímavé, takže umožňuje pomocí ladicího programu zjistit tento kód se zavřít.

5. Najeďte myší `Update` metoda dokud zeleným **spustit kliknutím** tlačítko ![spustit kliknutím](../debugger/media/dbg-tour-run-to-click.png "RunToClick") se zobrazí na levé straně.

     ![Použití spustit kliknutím funkce](../debugger/media/dbg-tour-run-to-click-2.png "spustit kliknutím")

    >  [!NOTE] 
    > **Spustit kliknutím** tlačítko je nového v [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]. Pokud se nezobrazí tlačítko zelenou šipku, použijte F11 v tomto příkladu posunut ladicího programu.

6. Klikněte **spustit kliknutím** tlačítko ![spustit kliknutím](../debugger/media/dbg-tour-run-to-click.png "RunToClick").

    Pomocí tohoto tlačítka se podobá nastavením dočasné zarážky. **Spustit kliknutím** je užitečný pro získání rychle v rámci viditelné oblasti kód aplikace (můžete kliknout na v jakékoli otevření souboru).

    Ladicí program přejde `Update` implementace metod.

7. Stisknutím klávesy F11 přejde do `Update` metoda.

     ![Výsledek zanoříte se do metodu aktualizace](../debugger/media/dbg-tour-update-method.png "krok do aktualizační metody")

    Zde se nám najít další kód, který vypadá zajímavé; aplikace je získávání všechny soubory *.jpg umístěných v jednom adresáři a pak vytvořit objekt fotografií pro každý soubor. Tento kód nám poskytuje dobrý moci spustit, zkontrolujte stav vaší aplikace (proměnné) s ladicím programem. Bude to v dalších částech tohoto kurzu.

    Funkce, které vám umožní prohlédnout proměnné jsou jedním z nejužitečnějších funkcí ladicího programu a provést různými způsoby. Často když se pokusíte ladění problém, pokoušíte zjistit, jestli jsou proměnné ukládání hodnoty, které mají mít v určitém čase očekáváte.

## <a name="examine-the-call-stack"></a>Prozkoumat zásobník volání

Při pozastavena v `Update` metoda, klikněte na tlačítko **zásobníkem volání** okno, které je ve výchozím nastavení otevřít v pravém dolním podokně.

![Prozkoumat zásobník volání](../debugger/media/dbg-tour-call-stack.png "ExamineCallStack")

**Zásobníkem volání** okno zobrazuje pořadí, ve kterém jsou získávání volat metody a funkce. Na začátek řádku ukazuje aktuální funkci ( `Update` metoda v aplikaci prohlídka). Druhý řádek ukazuje, že `Update` byla volána z `Path.set` vlastnost a tak dále.

>  [!NOTE]
> **Zásobníkem volání** okno se podobá ladění perspektivy v některé integrovaného vývojového prostředí jako Eclipse.

V zásobníku volání je dobrý způsob, jak prozkoumat a lépe pochopit tok spuštění aplikace.

Poklepáním na řádek kódu přejít, podívejte se na tomto zdrojovém kódu, která také změní aktuální obor ke kontrole pomocí ladicího programu. Tato akce není posunutí ladicího programu.

Můžete také klikněte pravým tlačítkem na nabídky z **zásobníkem volání** okno provádět další akce. Například můžete vložit zarážky do určených funkcí, zálohy pomocí ladicího programu **spustit ke kurzoru**a přejděte zkontrolujte zdrojového kódu. Další informace najdete v tématu [postup: prozkoumat zásobník volání](../debugger/how-to-use-the-call-stack-window.md).

## <a name="step-out"></a>Krok

Řekněme, že skončíte zkoumání `Update` metoda v Data.cs a vy chcete využívat funkce, ale zůstane v ladicím programu. Můžete provést pomocí **Krokovat s Vystoupením** příkaz.

1. Stiskněte Shift + F11 (nebo **ladění > Krok**).

     Tento příkaz obnoví spuštění aplikace (a posune ladění) až do aktuálního funkce vrátí hodnotu.

     Byste měli mít zpět `Update` volání metody v Data.cs.

2. Stiskněte Shift + F11 znovu a ladicí program vloží zásobníkem volání zpět do `OnApplicationStartup` obslužné rutiny události.

## <a name="run-to-cursor"></a>Spustit ke kurzoru

1. Vyberte **Zastavte ladění** červené tlačítko ![Zastavte ladění](../debugger/media/dbg-tour-stop-debugging.png "Zastavte ladění") nebo Shift + F5.

2. V `Update` metoda v Data.cs, klikněte pravým tlačítkem myši `Add` metoda volání a zvolte **spustit ke kurzoru**. Tento příkaz spustí, ladění a nastaví dočasné zarážek na aktuálním řádku kódu.

     ![Použití spustit funkci kurzor](../debugger/media/dbg-tour-run-to-cursor.png "spustit ke kurzoru")

    Jste měli pozastavena na zarážka v `MainWindow` (protože se první zarážky nastavit).

3. Stisknutím klávesy F5 přechodu na `Add` jste vybrali metodu **spustit ke kurzoru**.

    Tento příkaz je užitečné, pokud jsou úpravy kódu a chcete rychle zarážku dočasné a spuštění ladicího programu.

## <a name="change-the-execution-flow"></a>Tok provádění změn

1. S ladicím programem pozastavena na `Add` volání metody, pomocí myši můžete získat šipku žlutý (provádění ukazatel) na levé straně a přesunout žlutý šipka nahoru jeden řádek `foreach` smyčky.

     ![Přesuňte ukazatel provádění](../debugger/media/dbg-tour-move-the-execution-pointer.gif "přesunout ukazatel provádění")

    Změnou toku provádění můžete provést akce, jako je testovací cesty provádění různých kódu nebo znova spustí kód bez restartování ladicího programu.

2. Nyní stisknutím klávesy F5.

    Můžete zobrazit bitové kopie, přidány do okna aplikace. Protože jsou opětným spuštěním kódu v `foreach` smyčky, některé z bitové kopie přidané dvakrát!
    
    > [!WARNING]
    > Často budete muset pečlivě s touto funkcí a zobrazí upozornění v popisu tlačítka. Příliš se může zobrazit další upozornění. Přesunutí kurzoru nelze vrátit vaší aplikace do předchozího stavu aplikace.

## <a name="inspect-variables-with-data-tips"></a>Zkontrolujte proměnné s typy dat

1. Otevřete Data.cs v fotografií prohlížeč ukázkovou aplikaci, klikněte pravým tlačítkem myši `private void Update` deklaraci funkce a zvolte **spustit ke kurzoru** (zastavit aplikaci nejprve Pokud ještě není spuštěná).

    To se pozastaví aplikace s ladicím programem připojen. To umožňuje nám prozkoumat její stav.

2. Najeďte myší `Add` metoda volání a klikněte na tlačítko **spustit kliknutím** tlačítko ![spustit kliknutím](../debugger/media/dbg-tour-run-to-click.png "RunToClick").

3. Nyní, najeďte myší na objekt souboru (`f`) a zobrazí jeho výchozí hodnotu vlastnosti, název souboru `market 031.jpg`.

     ![Zobrazení dat tip](../debugger/media/dbg-tour-data-tips.gif "zobrazení dat tipu")

4. Rozbalte objekt můžete zobrazit její vlastnosti, jako `FullPath` vlastnost.

    Často při ladění, chcete rychle zkontrolovat hodnot vlastností objektů a typy dat jsou vhodný způsob, jak to provést.

    > [!TIP]
    > Ve nejvíce podporované jazyky můžete upravit kód uprostřed relaci ladicí program, pokud zjistíte, že něco, co chcete změnit. Další informace najdete v tématu [upravit a pokračovat](../debugger/edit-and-continue.md). Pokud chcete použít tuto funkci v této aplikaci, ale by nejprve musíme aktualizovat aplikace verzi rozhraní .NET Framework.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>Zkontrolujte proměnné s windows automobily a lokální proměnné

1. Podívejte se na **automobily** okna v dolní části editoru kódu.

     ![Zkontrolujte proměnné v okně automobily](../debugger/media/dbg-tour-autos-window.png "automatické hodnoty – okno")

    V **automobily** okně zobrazí proměnné a jejich aktuální hodnotu. **Automobily** v okně se zobrazí všechny proměnné použít u aktuálního řádku nebo předchozí řádek (v C++, zobrazí se v proměnné v předchozí tři řádky kódu. Podívejte se do dokumentace pro konkrétní jazyk chování).

    > [!NOTE]
    > V jazyce JavaScript **místní hodnoty –** okno je ale není podporovaná **automobily** okno.

2. Další, podívejte se na **místní hodnoty –** okno.

    **Místní hodnoty** v okně se zobrazí proměnné, které jsou v aktuálním oboru.

    ![Zkontrolujte proměnné v místní hodnoty – okno](../debugger/media/dbg-tour-locals-window.png "místní hodnoty – okno")

    V současné době `this` objekt a objekt souboru (`f`) jsou v aktuálním oboru. Další informace najdete v tématu [zkontrolovat proměnné v automobily a místní hodnoty – Windows](../debugger/autos-and-locals-windows.md).

## <a name="set-a-watch"></a>Nastavovat sledování

1. V okně editoru hlavní kódu, klikněte pravým tlačítkem na objekt souboru (`f`) a zvolte **Přidat kukátko**.

    Můžete použít **sledovat** okno určete proměnné (nebo výraz), kterou chcete sledovat na.

    Nyní máte sledovat, nastavit `File` objekt a můžete zobrazit jeho hodnotu změnit, protože pohyb ladicího programu. Na rozdíl od jiných proměnných windows **sledovat** okno vždy zobrazuje proměnné se díváte (jejich jste šedě při mimo rozsah).

2. Na `Add` metoda, klikněte na tlačítko se zeleným ![spustit kliknutím](../debugger/media/dbg-tour-run-to-click.png "RunToClick") tlačítko znovu (nebo stiskněte F11 několikrát) najděte `foreach` smyčky.

    ![Nastavovat sledování na proměnnou](../debugger/media/dbg-tour-watch-window.png "kukátko – okno")

    Můžete si také prohlédnout první obrázek se přidají do hlavního okna spuštění ukázkové aplikace, ale to se stane na vlákno jinou aplikaci, tak bitové kopie nemusí být zobrazeny ještě.

    Další informace najdete v tématu [nastavovat sledování pomocí sledování a QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)

## <a name="examine-an-exception"></a>Zkontrolujte výjimku

1. V okně spuštěné aplikace, odstraňte text v **cesta** vstupní pole a vyberte **změnu** tlačítko.

     ![Způsobí výjimku, která je vyvolána](../debugger/media/dbg-tour-cause-an-exception.png "výjimky")

     Vyvolá výjimku, aplikace a ladicí program přejdete na řádek kódu, která vrátila výjimku.
     
     ![Pomocníka výjimka](../debugger/media/dbg-tour-exception-helper.png "pomocníka výjimka")

     Zde **pomocníka výjimka** se dozvíte, `System.ArgumentException` a chybová zpráva s upozorněním, že cesta není právní formuláře. Ano víme, že k chybě došlo na argumentu metody nebo funkce.

     V tomto příkladu `DirectoryInfo` uvedl chyba na prázdný řetězec uložený v `value` proměnné. (Pozastavte ukazatel myši nad `value` zobrazíte prázdný řetězec.)

     Pomocníka výjimka je skvělé funkce, která vám může pomoct ladění chyb. Můžete také provádět akce podobně jako zobrazení Podrobnosti o chybě a přidat kukátko z pomocníka výjimka. Nebo v případě potřeby můžete změnit podmínky pro vyvolání konkrétní výjimka.

    >  [!NOTE] 
    > Pomocníka výjimka nahrazuje Pomocníka pro výjimky v [!include[vs_dev15](../misc/includes/vs_dev15_md.md)].

2. Rozbalte **nastavení výjimky** uzlu zobrazíte další možnosti o tom, jak zpracovávat tento typ výjimky, ale nebudete muset změnit všechno u této ukázky!

3. Stisknutím klávesy F5 aplikaci pokračovat.

Další informace o funkcích ladicího programu najdete v tématu [ladicí program tipy a triky](../debugger/debugger-tips-and-tricks.md).

## <a name="next-steps"></a>Další kroky

V tomto kurzu když jste se naučili postup spuštění ladicího programu, krok prostřednictvím kódu a zkontrolovat proměnné. Chcete získat přehled funkcí ladicího programu spolu s odkazy na další informace.

> [!div class="nextstepaction"]
> [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)

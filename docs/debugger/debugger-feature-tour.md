---
title: První seznámení s ladicím programem
description: Prohlédněte si rychlý různých funkcí ladicího programu sady Visual Studio.
ms.custom: mvc
ms.date: 03/27/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: c763d706-3213-494f-b4d2-990b6e1ec456
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de27a6b3fd5b182ac2fa0ad12ed04e4d1105d9ac
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34691089"
---
# <a name="first-look-at-the-visual-studio-debugger"></a>První pohled na Visual Studio Debugger

Toto téma představuje funkce ladicího programu sady Visual Studio. Pokud chcete sledovat otevřením vlastní aplikace v sadě Visual Studio, můžete to udělat, nebo můžete provést společně s ukázkové aplikace pomocí [začátečníka](../debugger/getting-started-with-the-debugger.md).

Funkce popsané tady platí pro C#, C++, Visual Basic, JavaScript a jiných jazyků – podpora Visual Studio (Pokud není uvedeno jinak).

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Nastavit zarážky a spuštění ladicího programu

Chcete-li ladit, spusťte aplikaci pomocí ladicího programu připojit k procesu aplikací. F5 (**ladění > Spustit ladění**) je nejběžnější způsob, jak to udělat. Ale vpravo teď nemusí mít nastavit všechny zarážky pro zjištění aplikace kódu, proto jsme se učinit nyní a pak spusťte ladění.

Pokud máte soubor otevřete v editoru kódu, můžete nastavit zarážky kliknutím na okraji nalevo od řádek kódu.

![Nastavit zarážky](../debugger/media/dbg-tour-set-a-breakpoint.gif "nastavit zarážky")

Stisknutím klávesy F5 (**ladění > Spustit ladění**) a ladicí program spustí první zarážku, který nalezne. Pokud ještě není aplikace spuštěna, F5 spuštění ladicího programu a zastaví u první zarážky.

Zarážky jsou užitečné funkce, když víte, řádek kódu nebo části kódu, který chcete prozkoumat podrobně.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>Přejděte kódu v ladicím programu pomocí příkazů krok

Poskytujeme klávesové zkratky pro většinu příkazů, protože navigační kódu aplikace rychlejší. (Ekvivalentní příkazy, například příkazy nabídky jsou uvedeny v závorkách.)

Aplikace s ladicím programem připojené, stiskněte F11 (**ladění > Krokovat s vnořením**). Je F11 **Krokovat s vnořením** příkazů a přejde jeden příkaz spuštění aplikace v čase. Při spuštění aplikace s F11, ladicího programu dělí na první příkaz, který získá provést.

![F11 Krok do](../debugger/media/dbg-tour-f11.png "F11 krok do")

Žlutý šipku představuje příkaz na kterém pozastavena ladicí program, který také pozastaví spuštění aplikace na stejném místě (Tento příkaz ještě spuštěna).

F11 je dobrý způsob, jak prozkoumat toku provádění většiny podrobně. (Pokud chcete přesunout rychlejší prostřednictvím kódu, jsme ukážeme některé další možnosti také.) Ve výchozím nastavení, přeskočí ladicího programu přes jiný uživatelský kód (Pokud chcete další podrobnosti, projděte si téma [pouze můj kód](../debugger/just-my-code.md)).

>[!NOTE]
> Ve spravovaném kódu zobrazí se dialogové okno s dotazem, zda chcete být upozorněni, když automaticky krok přes vlastnosti a operátory (výchozí nastavení). Pokud chcete změnit nastavení později, zakažte **krok přes vlastnosti a operátory** nastavení v **nástroje > Možnosti** nabídky v části **ladění**.

## <a name="step-over-code-to-skip-functions"></a>Krok přes kód, který přeskočí funkce

Pokud jste na řádek kódu, který je volání funkci nebo metodu, můžete stisknout F10 (**ladění > Krokovat s přeskočením**) namísto F11.

F10 Posune ladění bez zanoříte se do funkce nebo metody v kódu aplikace (kód stále provádí). Stisknutím klávesy F10, můžete přeskočit kód, který není vás zajímají. Tímto způsobem můžete rychle získat kódu, které vás zajímají další.

## <a name="step-into-a-property"></a>Krok do vlastnosti

Jak už bylo zmíněno dříve, ve výchozím nastavení ladicího programu přeskočí přes spravované vlastnosti a pole, ale **krok do konkrétní** příkaz umožňuje toto chování potlačit.

Klikněte pravým tlačítkem na vlastnost nebo pole a zvolte **krok do konkrétní**, pak vyberte jednu z dostupných možností.

![Krok do konkrétní](../debugger/media/dbg-tour-step-into-specific.png "krokování s vnořením konkrétní")

V tomto příkladu **krok do konkrétní** získá nám na kód pro `Path.set`.

![Krok do konkrétní](../debugger/media/dbg-tour-step-into-specific-2.png "krokování s vnořením konkrétní")

## <a name="run-to-a-point-in-your-code-quickly-using-the-mouse"></a>Spustit na bod v kódu rychle pomocí myši

V ladicím programu, najeďte myší na řádek kódu až **spustit kliknutím** (Spustit provádění sem) tlačítko ![spustit kliknutím](../debugger/media/dbg-tour-run-to-click.png "RunToClick") se zobrazí na levé straně.

![Spustit kliknutím](../debugger/media/dbg-tour-run-to-click-2.png "spustit kliknutím")

> [!NOTE]
> **Spustit kliknutím** tlačítko (Spustit provádění sem) je nového v [!include[vs_dev15](../misc/includes/vs_dev15_md.md)].

Klikněte **spustit kliknutím** tlačítko (Spustit provádění sem). Ladicí program přejde na řádek kódu, kde jste klikli na.

Pomocí tohoto tlačítka se podobá nastavením dočasné zarážky. Tento příkaz je také užitečné pro získání rychle v rámci viditelné oblasti kódu aplikace. Můžete použít **spustit kliknutím** v jakékoli otevření souboru.

## <a name="advance-the-debugger-out-of-the-current-function"></a>Ladicí program mimo funkci current posunutí

V některých případech můžete chtít pokračovat v relaci ladění ale zálohy ladicí program až aktuální funkce.

Stiskněte Shift + F11 (nebo **ladění > Krok**).

Tento příkaz obnoví spuštění aplikace (a posune ladění) až do aktuálního funkce vrátí hodnotu.

## <a name="run-to-cursor"></a>Spustit ke kurzoru

Zastavení ladicího programu stisknutím **Zastavte ladění** červené tlačítko ![Zastavte ladění](../debugger/media/dbg-tour-stop-debugging.png "Zastavte ladění") nebo Shift + F5.

Klikněte pravým tlačítkem myši na řádek kódu v aplikaci a vyberte **spustit ke kurzoru**. Tento příkaz spustí, ladění a nastaví dočasné zarážek na aktuálním řádku kódu.

![Spustit ke kurzoru](../debugger/media/dbg-tour-run-to-cursor.png "spustit ke kurzoru")

Pokud jste nastavili zarážky, ladicí program se pozastaví na první zarážce, kterou volání.

Stisknutím klávesy F5, dokud se nedostanete na řádek kódu, kde jste vybrali **spustit ke kurzoru**.

Tento příkaz je užitečné, pokud jsou úpravy kódu a chcete rychle zarážku dočasné a spuštění ladicího programu.

> [!NOTE]
> Můžete použít **spustit ke kurzoru** v **zásobníkem volání** okno při ladění.

## <a name="restart-your-app-quickly"></a>Restartujte aplikace rychle

Klikněte na tlačítko **restartujte** ![restartujte aplikace](../debugger/media/dbg-tour-restart.png "restartujte aplikace") tlačítka na panelu nástrojů Debug (**Ctrl + Shift + F5**).

Po stisknutí klávesy **restartujte**, ho šetří čas a zastavení aplikace a restartování ladicího programu. Ladicí program se pozastaví u první zarážky, který je dosáhl spuštěním kódu.

Pokud chcete vrátit do editoru kódu a zastavení ladicího programu, můžete stisknout red zastavení ![Zastavte ladění](../debugger/media/dbg-tour-stop-debugging.png "Zastavte ladění") tlačítko místo **restartujte**.

## <a name="inspect-variables-with-data-tips"></a>Zkontrolujte proměnné s typy dat

Teď, když hodně trochu znáte, máte funkční moci spustit, zkontrolujte stav vaší aplikace (proměnné) s ladicím programem. Funkce, které vám umožní prohlédnout proměnné jsou některé z nejužitečnějších funkcí ladicího programu a provést různými způsoby. Často když se pokusíte ladění problém, pokoušíte se zjistit, jestli jsou proměnné ukládání hodnoty, které očekáváte, že mají mít ve stavu, konkrétní aplikace.

Při pozastavena v ladicím programu, najeďte myší na objekt pomocí myši a zobrazí jeho výchozí hodnota vlastnosti (v tomto příkladu, název souboru `market 031.jpg` je výchozí hodnota vlastnosti).

![Zobrazení dat Tip](../debugger/media/dbg-tour-data-tips.gif "zobrazení dat tipu")

Rozbalte objekt můžete zobrazit její vlastnosti (například `FullPath` vlastnost v tomto příkladu).

Často při ladění, chcete rychle zkontrolovat hodnot vlastností objektů a typy dat jsou vhodný způsob, jak to provést.

> [!TIP]
> V nejvíce podporovaných jazyků můžete upravit kód uprostřed ladicí relace. Další informace najdete v tématu [upravit a pokračovat](../debugger/edit-and-continue.md).

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>Zkontrolujte proměnné s windows automobily a lokální proměnné

Při ladění, podívejte se na **automobily** okna v dolní části editoru kódu.

![Automatické hodnoty – okno](../debugger/media/dbg-tour-autos-window.png "automatické hodnoty – okno")

V **automobily** okně uvidíte proměnné spolu s jejich aktuální hodnotu a jejich typů. **Automobily** v okně se zobrazí všechny proměnné použít u aktuálního řádku nebo předchozí řádek (v C++, zobrazí se v proměnné v předchozí tři řádky kódu. Podívejte se do dokumentace pro konkrétní jazyk chování).

> [!NOTE]
> V jazyce JavaScript **místní hodnoty –** okno je ale není podporovaná **automobily** okno.

Další, podívejte se na **místní hodnoty –** okno. **Místní hodnoty** v okně se zobrazí proměnné, které jsou aktuálně v oboru.

![Místní hodnoty – okno](../debugger/media/dbg-tour-locals-window.png "místní hodnoty – okno")

V tomto příkladu `this` objekt a objekt `f` nacházejí v oboru. Další informace najdete v tématu [zkontrolovat proměnné v automobily a místní hodnoty – Windows](../debugger/autos-and-locals-windows.md).

## <a name="set-a-watch"></a>Nastavovat sledování

Můžete použít **sledovat** okno určete proměnné (nebo výraz), kterou chcete sledovat na.

Při ladění, klikněte pravým tlačítkem na objekt a zvolte **Přidat kukátko**.

![Okno kukátka](../debugger/media/dbg-tour-watch-window.png "kukátko – okno")

V tomto příkladu máte sledovat, nastavte na `f` objekt a můžete zobrazit jeho hodnotu změnit, protože pohyb ladicího programu. Na rozdíl od jiných proměnných windows **sledovat** windows vždy zobrazovat proměnné se díváte (jejich jste šedě při mimo rozsah).

Další informace najdete v tématu [nastavovat sledování pomocí sledování a QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)

## <a name="examine-the-call-stack"></a>Prozkoumat zásobník volání

Klikněte **zásobníkem volání** okno při ladění, který je ve výchozím nastavení otevřít v pravém dolním podokně.

![Prozkoumat zásobník volání](../debugger/media/dbg-tour-call-stack.png "prozkoumat zásobník volání")

**Zásobníkem volání** okno zobrazuje pořadí, ve kterém jsou získávání volat metody a funkce. Na začátek řádku ukazuje aktuální funkci ( `Update` metoda v tomto příkladu). Druhý řádek ukazuje, že `Update` byla volána z `Path.set` vlastnost a tak dále. V zásobníku volání je dobrý způsob, jak prozkoumat a lépe pochopit tok spuštění aplikace.

> [!NOTE]
> **Zásobníkem volání** okno se podobá ladění perspektivy v některé integrovaného vývojového prostředí jako Eclipse.

Poklepáním na řádek kódu přejít, podívejte se na tomto zdrojovém kódu, která také změní aktuální obor ke kontrole pomocí ladicího programu. Není to zálohy ladicího programu.

Můžete také klikněte pravým tlačítkem na nabídky z **zásobníkem volání** okno provádět další akce. Například můžete vložit zarážky do určité funkce, restartujte aplikace pomocí **spustit ke kurzoru**a abyste přešli zkontrolujte zdrojového kódu. V tématu [postup: prozkoumat zásobník volání](../debugger/how-to-use-the-call-stack-window.md).

## <a name="examine-an-exception"></a>Zkontrolujte výjimku

Pokud vaše aplikace vyvolá výjimku, ladicího programu přejdete na řádek kódu, která vrátila výjimku.

![Pomocníka výjimka](../debugger/media/dbg-tour-exception-helper.png "pomocníka výjimka")

V tomto příkladu **pomocníka výjimka** se dozvíte `System.Argument` výjimku a chybová zpráva s upozorněním, že cesta není právní formuláře. Ano víme, že k chybě došlo na argumentu metody nebo funkce.

V tomto příkladu `DirectoryInfo` uvedl chyba na prázdný řetězec uložený v `value` proměnné.

Pomocníka výjimka je skvělé funkce, která vám může pomoct ladění chyb. Můžete také provádět akce podobně jako zobrazení Podrobnosti o chybě a přidat kukátko z pomocníka výjimka. Nebo v případě potřeby můžete změnit podmínky pro vyvolání konkrétní výjimka.

>  [!NOTE]
> Pomocníka výjimka nahrazuje Pomocníka pro výjimky v [!include[vs_dev15](../misc/includes/vs_dev15_md.md)].

Rozbalte **nastavení výjimky** uzlu zobrazíte další možnosti o tom, jak zpracovávat tento typ výjimky, ale nebudete muset změnit všechno u této ukázky!

## <a name="debug-live-aspnet-apps-in-azure-app-service"></a>Ladění aplikací za provozu technologie ASP.NET ve službě Azure App Service

**ladicí program snímku** pořídí snímek aplikací v provozním když provede kód, který vás zajímá. Dáte pokyn, aby ladicí program na pořízení snímku, nastavte snappoints a logpoints ve vašem kódu. Ladicí program umožňuje zobrazit přesně kde došlo k chybě, bez vlivu na provoz produkční aplikace. Ladicí program snímku můžete výrazně zkrátit dobu potřebnou k vyřešení problémů, ke kterým došlo v produkčním prostředí.

![Spuštění ladicího programu snímku](../debugger/media/snapshot-launch.png "spuštění ladicího programu snímku")

Snímek kolekce je k dispozici pro aplikace ASP.NET, které jsou spuštěné v Azure App Service. Aplikace ASP.NET musí být spuštěn v rozhraní .NET Framework 4.6.1 nebo novější, a ASP.NET Core aplikace musí být spuštěná na .NET Core 2.0 nebo novější na systému Windows.

Další informace najdete v tématu [ladění za provozu aplikace ASP.NET pomocí ladicího programu snímku](../debugger/debug-live-azure-applications.md).

## <a name="view-snapshots-with-intellitrace-step-back-visual-studio-enterprise"></a>Zobrazení snímky s IntelliTrace krok zpětným (Visual Studio Enterprise)

**Zpětný krok IntelliTrace** automaticky vytvoří snímek vaší aplikace v každé zarážek a ladicí program krok události. Zaznamenaná snímky umožňují přejděte zpět na předchozí zarážky nebo kroky a zobrazení stavu aplikace, stejně jako tomu bylo v minulosti. IntelliTrace zpětný krok vám může ušetřit čas když chcete zobrazit předchozí stav aplikace, ale nechcete, aby se znovu spustit ladění nebo znovu vytvořte stav požadované aplikace.

Můžete vyhledat a zobrazit snímky pomocí **krok zpětné** a **krok dál** tlačítek na panelu nástrojů ladění. Tato tlačítka přejděte události, které se zobrazují v **události** ve **diagnostické nástroje** okno.

![Krok tlačítka vpřed a zpět](../debugger/media/intellitrace-step-back-icons-description.png  "krok zpět a jejich předávání tlačítka")

Další informace najdete v tématu [zobrazit snímky IntelliTrace zpětným krok pomocí](../debugger/how-to-use-intellitrace-step-back.md) stránky.

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste měli rychlý přehled mnoho funkcí ladicí program. Může být vhodné podrobnější pohled na tyto funkce pomocí ukázkové aplikace

> [!div class="nextstepaction"]
> [Další informace k ladění pomocí sady Visual Studio](../debugger/getting-started-with-the-debugger.md)

---
title: Zobrazit snímek pomocí zpětný krok IntelliTrace
ms.description: Learn how to take snapshots, and view snapshots with IntelliTrace step-back
ms.custom: mvc
ms.date: 05/01/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
ms.assetid: 7c60d929-d993-49dc-9db3-43b30be9912b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 68fec4e10d172f79908e57828c542a444d081b50
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="view-snapshots-using-intellitrace-step-back-in-visual-studio"></a>Zobrazení snímky IntelliTrace pomocí zpětným krok v sadě Visual Studio

Zpětný krok IntelliTrace automaticky vytvoří snímek vaší aplikace v každé zarážek a ladicí program krok události. Zaznamenaná snímky umožňují přejděte zpět na předchozí zarážky nebo kroky a zobrazení stavu aplikace, stejně jako tomu bylo v minulosti. IntelliTrace zpětný krok vám může ušetřit čas když chcete zobrazit předchozí stav aplikace, ale nechcete, aby se znovu spustit ladění nebo znovu vytvořte stav požadované aplikace.

Zpětný krok IntelliTrace je k dispozici od Visual Studio Enterprise 2017 verze 15,5 a vyšší a vyžaduje Windows 10 Anniversary Update nebo vyšší. Tato funkce se aktuálně podporuje pro ladění ASP.NET, WinForms, WPF, aplikace spravované konzoly a spravované třídy knihovny. Od verze Visual Studio 2017 Enterprise 15.7 preview 1, funkce je také podporována pro ASP.NET Core a .NET Core. Ladění aplikací UWP není aktuálně podporován.

V tomto kurzu provedete následující:

> [!div class="checklist"]
> * Povolit události Intellitrace a snímky
> * Přejděte pomocí příkazů zpětný krok a dalšího kroku události
> * Zobrazení událostí snímky
  
## <a name="enable-intellitrace-events-and-snapshots-mode"></a>Povolit režim události a snímky IntelliTrace 

1. Otevřete projekt ve Visual Studio Enterprise.

1. Otevřete **nástroje** > **možnosti** > **IntelliTrace** nastavení a vyberte možnost **IntelliTrace události a snímky** . 

    ![Povolit režim události IntelliTrace a snímky](../debugger/media/intellitrace-enable-snapshots.png "režim povolit události IntelliTrace a snímky")

1. Pokud chcete provést konfiguraci možností pro zobrazení snímky na výjimky, zvolte **IntelliTrace** > **Upřesnit** z **možnosti** dialogové okno.

    Tyto možnosti jsou dostupné od verze Visual Studio Enterprise 2017 verze 15.7.

    ![Konfigurace chování pro snímky na výjimky](../debugger/media/intellitrace-enable-snapshots-on-exceptions.png)

    Když povolíte události a snímky, pořizování snímků na výjimky je rovněž povolena ve výchozím nastavení. Snímky na výjimky můžete zakázat pomocí zrušením výběru **shromažďování snímků na události výjimky**. Pokud je tato funkce povolena, pořizování snímků pro neošetřených výjimek. Pro zpracovávaný výjimky jsou snímky pořizovat pouze v případě, že je vyvolána výjimka, a pokud není znovu vyvolání dříve vyvolána výjimka. Výběrem hodnoty z rozevíracího seznamu můžete nastavit maximální počet snímků na výjimky. Maximální počet se vztahuje na každém přechodu vaší aplikace do režimu pozastavení (například když aplikace dotkne zarážku).

    > [!NOTE]
    > Snímky jsou převzaty pouze pro výjimečné události tohoto záznamy IntelliTrace. Jaké události IntelliTrace záznamy můžete zadat tak, že vyberete **nástroje** > **možnosti** > **události IntelliTrace**.

1. V projektu, nastavte jeden nebo více zarážky a spuštění ladění (stiskněte **F5**), nebo spuštění ladění procházení kódu (**F10** nebo **F11**).

    IntelliTrace pořídí snímek proces aplikace na každý krok ladicí program, zarážek události a události neošetřené výjimky. Tyto události se zaznamenávají do **události** ve **diagnostické nástroje** okno, společně s další události IntelliTrace. Chcete-li otevřít toto okno, zvolte **ladění** > **Windows** > **zobrazit diagnostické nástroje**.

    Ikonu fotoaparátu se zobrazí vedle událostí, pro které snímky jsou k dispozici. 

    ![Události kartě se snímky](../debugger/media/intellitrace-events-tab-with-snapshots.png "kartu události s snímků zarážky a kroky")

    Z důvodů výkonu snímky nejsou provedeny, když je krok velmi rychle. Pokud se nezobrazí ikona fotoaparát vedle krok, zkuste krokování s pomaleji.

## <a name="navigate-and-view-snapshots"></a>Vyhledání a zobrazení snímky

1. Přecházet mezi jednotlivými události pomocí **krok zpět (Alt + [)** a **krok dál (Alt +])** tlačítek na panelu nástrojů ladění.

    Tato tlačítka přejděte události, které se zobrazují v **události** ve **okno diagnostické nástroje**. Krokování zpětně nebo dopředu na událost automaticky aktivuje [historické ladění](../debugger/historical-debugging.md) na vybrané události.

    ![Krok zpět a předávat tlačítka](../debugger/media/intellitrace-step-back-icons-description.png "tlačítka krok zpět a krok vpřed")

    Pokud krok zpět nebo krok dál, Visual Studio zadá historické ladění režimu. V tomto režimu kontextu ladicího programu přepne na čas, kdy byla zaznamenána zvolenou událost. Visual Studio také přesune ukazatele na odpovídající řádek kódu v okně zdroje. 

    V tomto zobrazení si můžete prohlédnout hodnoty v **zásobníkem volání**, **místní hodnoty –**, **automobily**, a **sledovat** systému windows. Můžete také najet přes proměnné, které chcete zobrazit datatips – a provádět vyhodnocení výrazu v **Immediate** okno. Data, která se zobrazí se ze snímku proces aplikace prováděné v tomto bodě v čase.

    Ano, například pokud jste dosáhl zarážku a provede krok (**F10**), **krok zpětné** tlačítko vloží Visual Studio v režimu historických na řádku kódu odpovídající na zarážku. 

    ![Aktivace historických režim událost snímek](../debugger/media/intellitrace-historical-mode-with-snapshot.png "aktivace historických režim událost snímku")

2. Pokud chcete vrátit do provozu provádění, zvolte **pokračovat (F5)** nebo klikněte na tlačítko **vrátit k živé ladění** odkaz v informačním panelu. 

3. Můžete také zobrazit snímek z **události** kartě. Chcete-li to provést, vyberte událost se snímek a klikněte na **aktivovat historické ladění**.

    ![Aktivovat historické ladění na událost](../debugger/media/intellitrace-activate-historical-debugging.png "aktivovat historické ladění na události")

    Na rozdíl od **další příkaz Set** příkazu, zobrazení snímku není znovu spusťte váš kód; nabízí statické zobrazení stavu aplikace na bod v čase, ke kterým došlo v minulosti.

    ![Přehled zpětný krok IntelliTrace](../debugger/media/intellitrace-step-back-overview.png "přehled nástroje IntelliTrace krok zpět")

    Další informace o tom, jak zkontrolovat proměnné v sadě Visual Studio najdete v tématu [prohlídka funkce ladicího programu](../debugger/debugger-feature-tour.md)  

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

#### <a name="how-is-intellitrace-step-back-different-from-intellitrace-events-only-mode"></a>Jak se liší od režimu jen pro události IntelliTrace IntelliTrace zpětným krok?

V režimu jen pro události IntelliTrace umožňuje aktivovat historické ladění na ladicí program a zarážky. Ale IntelliTrace zaznamená pouze data **místní hodnoty –** a **automobily** windows, pokud jsou otevřená okna a zaznamená pouze data, která je rozšířena a v zobrazení. V režimu jen pro události můžete často nemají úplný přehled o proměnné a komplexních objektů. Kromě toho výraz vyhodnocení a zobrazení dat v **sledovat** okno není podporován. 

V režimu události a snímky IntelliTrace zaznamená celý snímek proces aplikace, včetně složitých objektů. Na řádku kódu uvidíte stejné informace, jako kdyby byly zastavení na zarážce (a nezáleží, jestli dříve rozbalený informace). Vyhodnocení výrazu je podporováno také v případě zobrazení snímku.  

#### <a name="what-is-the-performance-impact-of-this-feature"></a>Co je dopad na výkon této funkce? 

Dopad na celkový výkon taktování závisí na vaší aplikace. Režijní náklady na pořízení snímku je přibližně 30 ms. Při pořízení snímku je forked proces aplikace a forked kopie je pozastaveno. Při zobrazení snímku, Visual Studio se připojuje k forked kopii proces. Pro každý snímek Visual Studio zkopíruje pouze tabulky stránky a nastaví stránky na kopii při zápisu. Pokud objekty v haldě změnit mezi ladicí program s přidružené snímky, tabulky příslušné stránky se pak zkopíruje, výsledkem je minimální paměti náklady. Pokud Visual Studio zjistí, že není dostatek paměti k pořízení snímku, nevyžaduje jeden.
 
## <a name="known-issues"></a>Známé problémy  
* Pokud používáte režim události a snímky IntelliTrace ve verzích systému Windows, které jsou starší než Windows 10 patří Creators aktualizace (RS3) a cílová platforma ladění aplikace je nastavena na x86, nevyžaduje snímky IntelliTrace.

    Alternativní řešení:
    * Instalaci nebo upgradu na Windows 10 patří Creators Update (RS3). 
    * Můžete taky: 
        1. Nainstalujte z instalačního programu Visual studio sadu nástrojů VC++ 2015.3 v140 pro desktop (x86, x64).
        2. Sestavte cílovou aplikaci.
        3. Z příkazového řádku pomocí nástroje editbin nástroje lze nastavit `Largeaddressaware` příznak pro cílový spustitelný soubor. Například můžete použít tento příkaz (po aktualizaci cesty): "C:\Program Files (x86) \Microsoft Visual Studio\Preview\Enterprise\VC\Tools\MSVC\14.12.25718\bin\Hostx86\x86\editbin.exe" / LARGEADDRESSAWARE "C:\Path\To\Application\app.exe".
        4. Chcete-li začít, ladění, stiskněte **F5**. Snímky jsou nyní pořízené ladicí program a zarážky.

        > [!Note]
        > `Largeaddressaware` Musí být nastaven příznak pokaždé, když spustitelný soubor je znovu sestaven pomocí změny.

* Při pořízení snímku proces aplikace na aplikaci, která používá trvalý soubor mapované paměti, proces se snímku obsahuje výhradní zámek souboru mapované paměti (i po nadřazeného procesu vydala jeho zámek). Další procesy, je stále moct číst, ale není zapisovat do souboru mapované paměti.

    Alternativní řešení:
    * Vymažte všechny snímky ukončením relace ladění. 

* Při ladění aplikace, jejichž proces má velký počet jedinečných paměti oblastech, jako je například aplikace, která načte velký počet knihoven DLL, krokování s snímků povolené výkon může být ovlivněno. Tento problém bude vyřešen v budoucí verzi systému Windows. Pokud se jedná o tento problém, oslovení nás na adrese stepback@microsoft.com. 

* Při ukládání souboru s **ladění > IntelliTrace > Uložit IntelliTrace relace** v režimu události a snímky další data zaznamenaná ze snímků není k dispozici v souboru .itrace. Na zarážek a krok události zobrazí stejné informace, jako kdyby měl uložili soubor v režimu jen pro události IntelliTrace. 

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste zjistili, jak používat zpětný krok IntelliTrace. Chcete další informace o dalších funkcích IntelliTrace.

> [!div class="nextstepaction"]
> [Funkce IntelliTrace](../debugger/intellitrace-features.md)

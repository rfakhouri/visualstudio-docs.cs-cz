---
title: "Zobrazit snímek pomocí kroku IntelliTrace-back - Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 12/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c60d929-d993-49dc-9db3-43b30be9912b
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c05905e8ffeec3aa699aac9dfa46c4b017b86be5
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2017
---
# <a name="view-snapshots-using-intellitrace-step-back"></a>Zobrazení snímky pomocí zpětný krok IntelliTrace
Zpětný krok IntelliTrace automaticky vytvoří snímek vaší aplikace v každé zarážek a ladicí program krok události. Zaznamenaná snímky umožňují přejděte zpět na předchozí zarážky nebo kroky a zobrazení stavu aplikace, stejně jako tomu bylo v minulosti. IntelliTrace zpětný krok vám může ušetřit čas když chcete zobrazit předchozí stav aplikace, ale nechcete, aby se znovu spustit ladění nebo znovu vytvořte stav požadované aplikace.

Zpětný krok IntelliTrace je k dispozici od Visual Studio Enterprise 2017 verze 15,5 a vyšší a vyžaduje Windows 10 Anniversary Update nebo vyšší. Tato funkce se aktuálně podporuje pro ladění ASP.NET, WinForms, WPF, aplikace spravované konzoly a spravované třídy knihovny. Ladění aplikací ASP.NET Core, .NET Core nebo UWP není aktuálně podporován. 
  
## <a name="enable-intellitrace-events-and-snapshots-mode"></a>Povolit režim události a snímky IntelliTrace 
Chcete-li povolit tuto funkci, přejděte na **nástroje > Možnosti > IntelliTrace** nastavení a vyberte možnost **IntelliTrace události a snímky**. 

![Povolit režim události IntelliTrace a snímky](../debugger/media/intellitrace-enable-snapshots.png "režim povolit události IntelliTrace a snímky")

IntelliTrace pořídí snímek proces aplikace na každý ladicí program krok a zarážek událostí. Tyto události se zaznamenávají do **události** ve **diagnostické nástroje** okno, společně s další události IntelliTrace. Chcete-li otevřít toto okno, zvolte **ladění / Windows / zobrazit diagnostické nástroje**.

Ikonu fotoaparátu se zobrazí vedle událostí, pro které snímky jsou k dispozici. 

![Události kartě se snímky](../debugger/media/intellitrace-events-tab-with-snapshots.png "kartu události s snímků zarážky a kroky")

Z důvodů výkonu snímky nejsou provedeny, když je krok velmi rychle. Pokud se nezobrazí ikona fotoaparát vedle krok, zkuste krokování s pomaleji.

## <a name="navigate-and-view-snapshots"></a>Vyhledání a zobrazení snímky

Mohou procházet mezi událostí pomocí **krok zpět (Alt + [)** a **krok dál (Alt +])** tlačítek na panelu nástrojů ladění. Tato tlačítka přejděte události, které se zobrazují v **události** ve **okno diagnostické nástroje**. Krokování zpětně nebo dopředu na událost automaticky aktivuje historické ladění na vybrané události.

![Krok zpět a předávat tlačítka](../debugger/media/intellitrace-step-back-icons-description.png "tlačítka krok zpět a krok vpřed")

Pokud krok zpět nebo krok dál, Visual Studio zadá historické ladění režimu. V tomto režimu kontextu ladicího programu přepne na čas, kdy byla zaznamenána zvolenou událost. Visual Studio také přesune ukazatele na odpovídající řádek kódu v okně zdroje. 

V tomto zobrazení si můžete prohlédnout hodnoty v **zásobníkem volání**, **místní hodnoty –**, **automobily**, a **sledovat** systému windows. Můžete také najet přes proměnné, které chcete zobrazit datatips – a provádět vyhodnocení výrazu v **Immediate** okno. Data, která se zobrazí se ze snímku proces aplikace prováděné v tomto bodě v čase.

Ano, například pokud jste dosáhl zarážku a provede krok (**F10**), **krok zpětné** tlačítko vloží Visual Studio v režimu historických na řádku kódu odpovídající na zarážku. 

![Aktivace historických režim událost snímek](../debugger/media/intellitrace-historical-mode-with-snapshot.png "aktivace historických režim událost snímku")

Pokud chcete vrátit do provozu provádění, zvolte **pokračovat (F5)** nebo klikněte na tlačítko **vrátit k živé ladění** odkaz v informačním panelu. 

Můžete také zobrazit snímek z **události** kartě. Vyberte událost snímek a klikněte na **aktivovat historické ladění**. Můžete také kliknutím na ikonu fotoaparátu aktivovat historické ladění.

![Aktivovat historické ladění na událost](../debugger/media/intellitrace-activate-historical-debugging.png "aktivovat historické ladění na události")

Na rozdíl od **další příkaz Set** příkazu, zobrazení snímku není znovu spusťte váš kód; nabízí statické zobrazení stavu aplikace na bod v čase, ke kterým došlo v minulosti.

![Přehled zpětný krok IntelliTrace](../debugger/media/intellitrace-step-back-overview.png "přehled nástroje IntelliTrace krok zpět")

## <a name="next-steps"></a>Další kroky  
 Informace o tom, chcete-li prověřit proměnné v sadě Visual Studio, najdete v části [prohlídka funkce ladicího programu](../debugger/debugger-feature-tour.md)  
 Přehled historické ladění najdete v tématu [historické ladění](../debugger/historical-debugging.md).  

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

* Při ukládání souboru s **ladění > IntelliTrace > Uložit IntelliTrace relace** v režimu události a snímky další data zaznamenaná ze snímků není k dispozici v souboru .itrace. Na zarážek a krok události zobrazí stejné informace, jako kdyby měl uložili soubor v režimu jen pro události IntelliTrace. 

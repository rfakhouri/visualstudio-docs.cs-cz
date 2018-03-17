---
title: IntelliTrace | Microsoft Docs
ms.custom: 
ms.date: 07/18/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.historicaldebug.overview
helpviewer_keywords:
- debugger, recording execution history
- debugging, recording execution history
- IntelliTrace [Visual Studio ALM]
- IntelliTrace, debugging applications
- debugger, (See also IntelliTrace [Visual Studio ALM])
- debugging, (See also IntelliTrace [Visual Studio ALM])
- IntelliTrace, collecting data from Test Manager
- IntelliTrace
- Test Manager, debugging with IntelliTrace
- IntelliTrace, debugging after a crash
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8f4edf6c446bdcd35585a60d97965d2d6ee21ad1
ms.sourcegitcommit: 236c250bb97abdab99d00c6525d106fc0035d7d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/17/2018
---
# <a name="intellitrace"></a>IntelliTrace

Strávíte méně času ladění aplikace při použití IntelliTrace zaznamenávat a sledování historie provádění vašeho kódu. Chyby můžete snadno najít, protože IntelliTrace umožňuje:

- Zaznamenat určité události

     Kontrola souvisejících kódu, data, která se zobrazí v **místní hodnoty –** okno během události ladicího programu a informace o volání funkce

- Ladění chyb, které jsou těžko reprodukci nebo který dojít v nasazení

Můžete vytvořit IntelliTrace ve Visual Studio Enterprise edition (ale ne edice Professional nebo komunity).

## <a name="what-do-you-want-to-do"></a>Co chcete udělat?

|||
|-|-|
|**Ladění Moje aplikace s použitím technologie IntelliTrace:**<br /><br /> -Zobrazit mi po události.<br />-Zobrazit mi volání informace s posledních událostí.<br />-Uložte Moje relace IntelliTrace.<br />– Ovládací prvek data, která shromažďuje IntelliTrace.|- [Návod: Použití IntelliTrace](../debugger/walkthrough-using-intellitrace.md)<br />- [Funkce IntelliTrace](../debugger/intellitrace-features.md)<br />- [Historické ladění](../debugger/historical-debugging.md)<br />- [Zobrazení snímky pomocí zpětný krok IntelliTrace](../debugger/how-to-use-intellitrace-step-back.md)|
|**Shromáždění dat technologie IntelliTrace během relace testu v Test Manager**|- [Shromažďování více diagnostických dat v manuálních testech](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)|
|**Shromáždění dat technologie IntelliTrace z nasazené aplikace**|- [Použití samostatného kolektoru IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md)|
|**Spusťte ladění ze souboru protokolu IntelliTrace (.iTrace soubor).**|- [Pomocí uložených dat technologie IntelliTrace](../debugger/using-saved-intellitrace-data.md)|

## <a name="IntelliTraceSupport"></a> Které aplikace můžete ladit s použitím technologie IntelliTrace

|||
|-|-|
|**Podporované**|– Visual Basic a Visual C# aplikace, které používají rozhraní .NET Framework 2.0 nebo vyšší verze.<br/>Můžete ladit většina aplikace, včetně ASP.NET, Microsoft Azure, Windows Forms, WCF, WPF, pracovní postup prostředí Windows, SharePoint 2010, SharePoint 2013 a 64bitová verze aplikace.<br/>K ladění aplikací služby SharePoint s použitím technologie IntelliTrace, najdete v části [návod: ladění aplikace SharePoint pomocí IntelliTrace pomocí](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md).<br/> Chcete-li ladit aplikace Microsoft Azure s použitím technologie IntelliTrace, přečtěte si téma [ladění je publikována Cloudová služba se IntelliTrace a Visual Studio](/azure/vs-azure-tools-intellitrace-debug-published-cloud-services).|
|**Omezená podpora**|-.NET core a ASP.NET Core aplikace podporována pro určité pouze události (řadiče MVC, ADO.NET a HTTPClicent událostí) v místní ladění. Samostatné kolekce není podporována pro .NET Core a ASP.NET Core aplikací.<br />-F # aplikace jako pokusné<br />-Aplikace UWP podporované pro pouze události|
|**Nepodporuje se**|-C++, jiných jazyků a skriptu<br />-Služby systému Windows, Silverlight, Xbox, nebo [!INCLUDE[winmobile](../debugger/includes/winmobile_md.md)] aplikace|

> [!NOTE]
> Pokud chcete ladit procesu, který je již spuštěn, můžete shromažďovat jenom události IntelliTrace (žádné informace volání). Můžete připojit 32bitovou nebo 64bitovou procesu v místním počítači. Události, které nastaly předtím, než můžete připojit k procesu nejsou shromážděna.

##  <a name="IntelliTraceVSTraditional"></a> Proč ladit s použitím technologie IntelliTrace?

Tradiční nebo *live* ladění zobrazuje pouze aplikace aktuální stav, s omezenou data o posledních událostí. Nemáte buď odvození tyto události na základě aktuálního stavu aplikace, nebo budete muset znovu vytvořit tyto události opětovným spuštěním aplikace.

Nástroj IntelliTrace rozšiřuje toto tradiční ladění zaznamenáváním určitých událostí a dat v těchto bodech v čase. To umožňuje zobrazit, co se stalo ve vaší aplikaci bez restartování, zejména v případě, že krok po kde je chybě. Nástroj IntelliTrace je ve výchozím nastavení zapnutý při tradičním ladění a shromažďuje data automaticky a transparentně. To umožňuje snadno přepínat mezi tradičním laděním a laděním pomocí nástroje IntelliTrace a zobrazovat zaznamenané informace. V tématu [funkce IntelliTrace](../debugger/intellitrace-features.md) a [jaká data shromažďování IntelliTrace?](#WhatData)

Nástroj IntelliTrace vám také může pomoci ladit chyby, které je těžké reprodukovat nebo ke kterým dochází při nasazování. Můžete shromažďovat data IntelliTrace a ukládat je do souboru protokolu IntelliTrace (soubor .iTrace). Soubor .iTrace obsahuje podrobnosti o výjimkách, událostech souvisejících s výkonem, webových požadavcích, testovacích datech, vláknech, modulech a další systémové informace. Můžete otevřít tento soubor v aplikaci Visual Studio Enterprise, vyberte položku a spuštění ladění pomocí technologie IntelliTrace. To vám umožní přejít na libovolnou událost v souboru a zobrazit konkrétní podrobnosti o aplikaci v tomto bodě v čase.

Můžete ukládat data IntelliTrace z těchto zdrojů:

- Relaci IntelliTrace ve Visual Studio 2017 Enterprise, Visual Studio 2015 Enterprise nebo předchozí verze Visual Studio Ultimate.

- Relace testování v Microsoft Test Manager

- Webové aplikace ASP.NET jsou hostovány službou IIS, nebo SharePoint 2010 a SharePoint 2013 spuštěnými v nasazení při použití nástroje Microsoft Monitoring Agent, buď samostatně, nebo s nástrojem System Center 2012. V tématu [použití samostatného kolektoru IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md) a [monitorování pomocí agenta Microsoft Monitoring Agent](http://technet.microsoft.com/library/dn465153.aspx).

 Zde je několik příkladů, jak nástroj IntelliTrace může pomoci s laděním:

- Aplikace má poškozený datový soubor, ale nevíte, kde došlo k této události.

     Bez IntelliTrace třeba prostřednictvím kódu můžete najít všechny možné soubor přístupů, umístí zarážky těchto přístupů a znovu spusťte aplikaci najít, kde došlo k problému. S použitím technologie IntelliTrace se zobrazí všechny události shromážděné přístupu k souborům a konkrétní podrobnosti o aplikaci při každé události.

- Dochází k výjimce.

     Bez IntelliTrace se zobrazí zpráva o výjimce, ale nemáte velkého množství informací o událostech, které vedly k výjimce. Můžete zkontrolovat zásobníku volání zobrazíte vzniklý řetěz volání, které vedly k výjimku, ale nemůžete zobrazit posloupnost událostí, ke kterým došlo během těchto volání. Pomocí nástroje IntelliTrace můžete zkoumat události, ke kterým došlo před výjimkou.

- Vaše aplikace dojde k chybě v testovacím počítači, ale na vývojovém počítači, spouští úspěšně.

     Můžete shromáždit data IntelliTrace z nástroje Microsoft Test Manager, uložit tato data do souboru .iTrace a připojit tento soubor k pracovní položce serveru Team Foundation Server pro pozdější zkoumání. V tématu [shromažďování více diagnostických dat v manuálních testech](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests) a [použít uložené dat technologie IntelliTrace](../debugger/using-saved-intellitrace-data.md).

- V nasazení aplikace se stane chyb nebo selhání.

     Pro aplikace Microsoft založené na Azure můžete nakonfigurovat kolekce dat IntelliTrace před publikováním aplikace. Při spuštění vaší aplikace IntelliTrace data uloží do souboru .iTrace. V tématu [ladění publikované Cloudová služba se IntelliTrace a Visual Studio](http://go.microsoft.com/fwlink/?LinkID=262248).

     V případě webových aplikací ASP.NET hostovaných ve službě IIS 7.0, 7.5 a 8.0 a aplikací služby SharePoint 2010 a SharePoint 2013 použijte nástroj Microsoft Monitoring Agent samotný nebo s nástrojem System Center 2012 k ukládání dat nástroje IntelliTrace do souboru .iTrace.

     To je užitečné, pokud chcete diagnostikovat problémy s aplikacemi v nasazení. V tématu [použití samostatného kolektoru IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md).

##  <a name="WhatData"></a> Jaká data IntelliTrace shromáždit?

**Shromažďování informací o události**

Ve výchozím nastavení, IntelliTrace zaznamenává pouze události IntelliTrace: ladicího programu události, výjimky, události rozhraní .NET Framework a jiné systémové události, které vám mohou pomoci s laděním. Můžete zvolit druhy událostí IntelliTrace, které chcete shromažďovat. Události ladicího programu a výjimky jsou shromažďovány vždy. V tématu [funkce IntelliTrace](../debugger/intellitrace-features.md).

- **Události ladicí program**

     Nástroj IntelliTrace vždy zaznamenává události, ke kterým dochází v ladicím programu sady Visual Studio. Spuštění aplikace je například událost ladicí program. Další ladicí program události jsou zastavování události, které způsobit přerušení spuštění aplikace. Například váš program dotkne zarážku, přístupy tracepoint nebo provede **krok** příkaz.

     Ve výchozím nastavení abyste s výkonem, IntelliTrace není záznam každých možná hodnota pro událost ladicí program. Zaznamenává pouze tyto hodnoty:

    - Hodnoty v **místní hodnoty –** okno. Zachovat **místní hodnoty –** okno Otevřít zobrazíte tyto hodnoty.

    - Hodnoty v **automobily** pouze v případě okno **automobily** je otevřené okno

    - Hodnoty v Datových tipech, které se zobrazují při přesunutí ukazatele myši nad proměnnou v okně zdroje s cílem zobrazit její hodnotu. Nástroj IntelliTrace neshromažďuje hodnoty v připnutých Datových tipech.

    Když je povolený režim události IntelliTrace a snímky, IntelliTrace budou pořízení snímku proces aplikace v každém ladicí program **zarážek** a **krok** událostí. To bude záznam hodnoty v **místní hodnoty –**, **automobily**, a **sledovat** windows, bez ohledu na to, jestli jsou windows otevřené nebo ne. Hodnoty v jakékoli definovaného datových tipech bude také shromažďovat.

- **Výjimky**

     Nástroj IntelliTrace zaznamenává typ výjimky a zprávu pro tyto druhy výjimek:

    - Zpracované výjimky, když je výjimka vyvolána a zachycena

    - Nezpracované výjimky

- **Události rozhraní .NET framework**

     Standardně nástroj IntelliTrace zaznamenává nejběžnější události rozhraní .NET Framework. Příklad:

    - V případě události Zaškrtnutí políčka shromažďuje nástroj IntelliTrace stav zaškrtávacího políčka a text.

- **Události aplikace SharePoint 2010 a SharePoint 2013**

     Můžete zaznamenat události uživatelského profilu a podmnožinu událostí sjednoceného systému protokolování (ULS) pro aplikace SharePoint 2010 a 2013 spuštěné mimo aplikaci Visual Studio. Tyto události můžete uložit do souboru .iTrace. Vyžaduje Visual Studio Enterprise 2017, Visual Studio Enterprise 2015, předchozí verzi Visual Studio Ultimate, nebo [agenta Microsoft Monitoring Agent](http://go.microsoft.com/fwlink/?LinkId=320384) spuštěné v **trasování** režimu.

     Po otevření souboru .iTrace zadejte ID korelace SharePoint a najděte odpovídající webový požadavek, zobrazte zaznamenané události a spusťte ladění od určité události. Obsahuje-li soubor neošetřené výjimky, lze ID korelace vybrat pro ladění výjimky.

     Další informace:

    - [Použití samostatného kolektoru IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md)

    - [Použití uložených dat řešení IntelliTrace](../debugger/using-saved-intellitrace-data.md)

    - [Návod: Ladění aplikace SharePoint s použitím technologie IntelliTrace](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)

**Zachycení snímků**

Můžete nakonfigurovat IntelliTrace a zachycení snímků u každé zarážky ladicího programu krok události. IntelliTrace zaznamenává úplném stavu aplikace na každý snímek, který vám umožní zobrazit komplexní proměnných a k vyhodnocení výrazů.

V tématu [zobrazit snímky IntelliTrace zpětným krok pomocí](../debugger/how-to-use-intellitrace-step-back.md).

**Shromažďovat informace o volání funkce**

Nástroj IntelliTrace můžete nakonfigurovat na shromažďování informací o volání funkcí. Tyto informace umožňují zobrazit historii zásobníku volání a umožňují krokovat zpět a vpřed mezi voláními v kódu. Pro každé volání funkce nástroj IntelliTrace zaznamenává tato data:

- Název funkce
- Hodnoty primitivních datových typů předané jako parametry na vstupech funkcí a vrácené na výstupech funkcí
- Hodnoty automatických vlastností při jejich čtení nebo změně
- Ukazatele na podřízené objekty první úrovně, avšak nikoli jejich hodnoty, ale pouze to, zda je jejich hodnota null

> [!NOTE]
> IntelliTrace shromažďuje pouze prvních 256 objektů v polích a prvních 256 znaků v řetězcích.

V tématu [zkontrolovat vaší aplikace pomocí historické ladění](../debugger/historical-debugging-inspect-app.md).

**Shromažďovat informace o modulu**

Pro řízení množství informací o voláních shromažďovaných nástrojem IntelliTrace zadejte pouze ty moduly, které vás zajímají. To může pomoct zlepšit výkon aplikace během kolekce. Najdete v části [řízení množství informací IntelliTrace shromažďuje](../debugger/intellitrace-features.md#ControlCallData) v funkce IntelliTrace.

## <a name="AffectPerformance"></a> Bude IntelliTrace zpomalit Moje aplikace?

Nástroj IntelliTrace standardně shromažďuje pouze data pro vybrané události IntelliTrace. Tato operace může nebo nemusí zpomalovat práci na vaší aplikace, v závislosti na strukturu a organizace kódu. Například pokud IntelliTrace zaznamená událost často, může dojít ke zpomalení vaší aplikace. Může mít také můžete zvážit refaktoring vaší aplikace.

Shromažďování informací o volání může aplikace výrazně zpomalit. Může také dojít ke zvětšení všech souborů protokolu IntelliTrace (.iTrace) ukládaných na disk. Pro minimalizaci negativních dopadů shromažďujte informace o volání pouze u modulů, které vás zajímají.  Chcete-li změnit maximální velikost vaše soubory .iTrace, přejděte na **nástroje**, **možnosti**, **IntelliTrace**, **Upřesnit**. 

## <a name="in-this-section"></a>V tomto oddílu

[Funkce IntelliTrace](../debugger/intellitrace-features.md)
[Diagnostika problémů po nasazení](../debugger/diagnose-problems-after-deployment.md)
[použít uložené dat technologie IntelliTrace](../debugger/using-saved-intellitrace-data.md)

### <a name="blogs"></a>Blogy

[Visual Studio ALM + Team Foundation Server](http://go.microsoft.com/fwlink/?LinkID=201340)

### <a name="forums"></a>Diskuzní fóra

[Visual Studio Diagnostics](http://go.microsoft.com/fwlink/?LinkId=262263)

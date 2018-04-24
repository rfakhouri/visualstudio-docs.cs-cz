---
title: Profilace rychlé webové stránky pomocí VSPerfASPNETCmd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- proflilng tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a7ebff923667f76c350f17a08196369b4354151d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="rapid-web-site-profiling-with-vsperfaspnetcmd"></a>Pohotová profilace webových stránek pomocí VSPerfASPNETCmd

**VSPerfASPNETCmd** nástroj pro příkazový řádek vám umožňuje snadno profil [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace. Ve srovnání s [VSPerfCmd](../profiling/vsperfcmd.md) nástroj pro příkazový řádek, jsou omezeny možnosti, musí být nastaveny žádné proměnné prostředí a není vyžadováno restartování počítače. Pomocí **VSPerfASPNETCmd** upřednostňovanou metodou pro profilace samostatných profileru. Další informace najdete v tématu [postupy: Instalace samostatného profileru](../profiling/how-to-install-the-stand-alone-profiler.md).

> [!NOTE]
> Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

 V některých případech, například shromažďování dat souběžnosti nebo pozastavení a obnovení profily, pomocí **VSPerfCmd** je upřednostňovaná metoda profilování.

> [!NOTE]
> Nástroje příkazového řádku balíku nástrojů pro profilaci jsou umístěny v podadresáři \Team Tools\Performance Tools instalačního adresáře sady Visual Studio. V 64bitových počítačích použijte nástroj VSPerfASPNETCmd umístěný v adresáři 32bitové \Team Tools\Performance nástroje. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).

## <a name="profiling-an-aspnet-application"></a>Profilace aplikací ASP.NET

Do profilu [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace, zadejte jeden z příkazů popsané v následujících částech. Webový server je spuštěn a profileru začne shromažďovat data. Výkon aplikace a pak zavřete prohlížeč. Profilace zastavíte stisknutím klávesy Enter v okně příkazového řádku.

> [!NOTE]
> Ve výchozím nastavení, nevrátí příkazovém řádku po **vsperfaspnetcmd** příkaz. Můžete použít **/nowait** možnost vynutit vrátit příkazového řádku. V tématu [pomocí možnosti/nowait](#UsingNoWait).

## <a name="to-collect-application-statistics-by-using-the-sampling-method"></a>Ke shromažďování statistik aplikace pomocí metody vzorkování
 Vzorkování je výchozí metody profilace **VSPerfASPNETCmd** nástroje a není potřeba zadat na příkazovém řádku. Následující příkazový řádek shromažďuje statistiky aplikace ze zadané webové aplikace:

 **vsperfaspnetcmd**  *websiteUrl*

## <a name="to-collect-detailed-timing-data-by-using-the-instrumentation-method"></a>Shromažďování podrobných dat časování pomocí metody instrumentace

Použijte následující příkazový řádek ke shromažďování podrobných dat časování z dynamicky kompilované [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace:

**/ trace vsperfaspnetcmd***websiteUrl* 

Pokud chcete profil soubory DLL staticky kompilované webové aplikace, musí instrumentace soubory pomocí [vsinstr –](../profiling/vsinstr.md) nástroj příkazového řádku. Příkaz/trace vsperfaspnetcmd bude obsahovat data z instrumentovaného souborů.

## <a name="to-collect-net-memory-data"></a>Ke shromažďování dat paměti .NET

**/Memory** možnost shromažďuje data o přidělení objektů v paměti .NET a můžete shromažďovat data o dobu trvání těchto objektů. Shromažďování dat přidělení je výchozí režim **/Memory** data možnost a není potřeba zadat na příkazovém řádku.

 **vsperfaspnetcmd /memory** *websiteUrl*

 Použití **životnost** parametr kromě shromažďování životnosti objektů přidělení dat:

 **vsperfaspnetcmd /memory:lifetime** *websiteUrl*

 Můžete také **/trasování** možnost zahrnout časování podrobné informace, pomocí dat paměti .NET:

 **vsperfaspnetcmd /memory**[**: doba platnosti**]   **/trasování**`websiteUrl`

## <a name="to-collect-tier-interaction-data"></a>Ke shromažďování dat interakce vrstev

> [!WARNING]
> Pomocí libovolná edice sady Visual Studio se můžou shromažďovat data (TIP) profilace sledováním interakce vrstev. Data profilace sledováním interakce vrstev však lze zobrazit pouze ve Visual Studio Enterprise.
>
> Chcete-li shromažďovat TIP data ve Windows 8 nebo Windows Server 2012, je nutné použít instrumentace (**/trasování**) možnost.

Ke shromažďování dat interakce vrstev s vzorkování dat:

**vsperfaspnetcmd /tip** `websiteUrl`

Ke shromažďování dat interakce vrstev s daty instrumentace:

**/ trace /tip vsperfaspnetcmd** *websiteUrl*

Ke shromažďování dat interakce vrstev s dat paměti .NET:

**vsperfaspnetcmd /memory**[**: doba platnosti**] *  */tip *** websiteUrl*

## <a name="UsingNoWait"></a> Pomocí možnosti/nowait

Ve výchozím nastavení, nevrátí příkazovém řádku po **vsperfaspnetcmd** příkaz. Možnost následující syntaxe můžete vynutit vrátit příkazového řádku. Pak můžete dělat jiné operace v okně příkazového řádku. Pokud chcete ukončit profilace, použijte **/Shutdown** možnost v samostatném **vsperfaspnetcmd** příkaz.

Chcete-li začít, profilace:

**vsperfaspnetcmd** [*/Options*] **/nowait***websiteUrl*

Pro ukončení profilace:

**/ vsperfaspnetcmd Shutdown** *websiteUrl*

## <a name="additional-options"></a>Další možnosti

Lze přidat kterýkoliv z následujících možností pro příkazy uvedené dříve v této části, s výjimkou **/vsperfaspnetcmd Shutdown** příkaz.

|Možnost|Popis|
|------------|-----------------|
|**/ Výstup:** `VspFile`|Ve výchozím nastavení, profilaci soubor dat (.vsp) se vytvoří v aktuálním adresáři s názvem souboru **PerformanceReport.vsp**. Pomocí možnosti Output můžete zadat jiné umístění, název souboru nebo obojí.|
|**/ PackSymbols: vypnuto**|Ve výchozím nastavení vloží VsPerfASPNETCmd symboly (funkce a názvy parametrů atd.) v souboru .vsp. Vložení symboly můžete nastavit, profilaci datového souboru velké. Pokud budete mít přístup k soubory PDB, které obsahují symboly při analýze dat, použijte /packsymbols: vypnout možnost zakázat, vkládání symboly.|

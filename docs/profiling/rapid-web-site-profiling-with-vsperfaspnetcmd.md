---
title: Profilování rychlých webů pomocí VSPerfASPNETCmd | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- proflilng tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5f86ae2e14067a645bb39a1c8fdc0421f415a9e6
ms.sourcegitcommit: 5694c5236fa32ba7f5bc1236a853f725ec7557e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2019
ms.locfileid: "68681136"
---
# <a name="rapid-web-site-profiling-with-vsperfaspnetcmd"></a>Rychlé profilování webu pomocí VSPerfASPNETCmd

Nástroj příkazového řádku **VSPerfASPNETCmd** umožňuje snadno profilovat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace. V porovnání s nástrojem příkazového řádku [VSPerfCmd](../profiling/vsperfcmd.md) jsou možnosti sníženy, není nutné nastavit žádné proměnné prostředí a restartování počítače není vyžadováno. Použití **VSPerfASPNETCmd** je upřednostňovanou metodou pro profilování pomocí samostatného profileru. Další informace najdete v tématu [jak: Nainstalujte samostatný Profiler](../profiling/how-to-install-the-stand-alone-profiler.md).

> [!NOTE]
> Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Podívejte [se na nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

 V některých scénářích, jako je například shromažďování souběžných dat nebo pozastavení a obnovení profilování, používá **VSPerfCmd** upřednostňovanou metodu profilace.

> [!NOTE]
> Postup získání cesty k nástrojům pro profilaci najdete v tématu [Určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Na 64bitových počítačích jsou k dispozici 64bitové i 32bitové verze nástrojů. Použití nástroje příkazového řádku profileru, musíte přidat cestu k nástrojům do proměnné prostředí PATH v okně příkazového řádku nebo ho přidejte do příkazu samého.

## <a name="profile-an-aspnet-application"></a>Profilování aplikace ASP.NET

Chcete-li [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] profilovat webovou aplikaci, zadejte jeden z příkazů popsaných v následujících částech. Web se spustí a Profiler začne shromažďovat data. Cvičení aplikace a následné zavření prohlížeče. Chcete-li zastavit profilaci, stiskněte klávesu **ENTER** v okně příkazového řádku.

> [!NOTE]
> Ve výchozím nastavení se příkazový řádek nevrátí po příkazu **VSPerfASPNETCmd** . Pomocí možnosti **/nowait** můžete vynutit, aby se příkazový řádek vrátil. Viz [použití možnosti/nowait](#use-the-nowait-option).

## <a name="to-collect-application-statistics-by-using-the-sampling-method"></a>Shromažďování statistik aplikace pomocí metody vzorkování
 Vzorkování je výchozí metoda profilování nástroje **VSPerfASPNETCmd** a není nutné ji zadávat v příkazovém řádku. Následující příkazový řádek shromažďuje statistiku aplikace ze zadané webové aplikace:

 **vsperfaspnetcmd**  *websiteUrl*

 Příkladem místních *websiteUrl* hostovaných na serveru může být *http://localhost/MySite/default.aspx* . Příkladem externího webu je *http://www.contoso.com* . Další informace najdete v ukázkových adresách URL v tématu profilace webu [bez otevření projektu v aplikaci Visual Studio](how-to-collect-performance-data-for-a-web-site.md#to-profile-a-web-site-without-opening-a-project-in-visual-studio).

## <a name="to-collect-detailed-timing-data-by-using-the-instrumentation-method"></a>Shromažďování podrobných dat časování pomocí metody instrumentace

K získání podrobných dat časování z dynamicky kompilované [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace použijte následující příkazový řádek:

**VSPerfASPNETCmd/Trace** *websiteUrl*

Chcete-li profilovat staticky kompilováno. soubory *DLL* ve webové aplikaci, je nutné instrumentovat soubory pomocí nástroje příkazového řádku [VSInstr](../profiling/vsinstr.md) . Příkaz VSPerfASPNETCmd/Trace bude obsahovat data z instrumentované soubory.

## <a name="to-collect-net-memory-data"></a>Shromažďování dat paměti .NET

Možnost **/Memory** shromažďuje data o přidělení objektů v paměti .NET a může shromažďovat data o životnosti těchto objektů. Kolekce dat přidělení je výchozím režimem možnosti dat **/Memory** a není nutné ji zadávat v příkazovém řádku.

 **VSPerfASPNETCmd/Memory** *websiteUrl*

 K shromažďování dat o životnosti objektu kromě dat přidělení použijte parametr **Doba života** :

 **VSPerfASPNETCmd/Memory: doba života** *websiteUrl*

 Pomocí možnosti **/Trace** můžete také zahrnout podrobné informace o časování s daty paměti .NET:

 **VSPerfASPNETCmd/Memory** [ **: doba života**] **/Trace**`websiteUrl`

## <a name="to-collect-tier-interaction-data"></a>Shromažďování dat interakce vrstev

> [!WARNING]
> Data profilování interakce vrstev (TIP) je možné shromažďovat pomocí libovolné edice sady Visual Studio. Data profilování interakce vrstev ale můžete zobrazit jenom v Visual Studio Enterprise.
>
> Chcete-li shromáždit data tipu v systému Windows 8 nebo Windows Server 2012, je nutné použít možnost instrumentace ( **/Trace**).

Shromažďování dat interakce vrstev s daty vzorkování:

**VSPerfASPNETCmd/Tip**`websiteUrl`

Shromažďování dat interakce vrstev s daty instrumentace:

**vsperfaspnetcmd /trace /tip** *websiteUrl*

Shromažďování dat interakce vrstev s daty paměti .NET:

**VSPerfASPNETCmd/Memory** [ **: doba života**] **/Tip** _websiteUrl_

## <a name="use-the-nowait-option"></a>Použití možnosti/NoWait

Ve výchozím nastavení se příkazový řádek nevrátí po příkazu **VSPerfASPNETCmd** . Pomocí následující možnosti syntaxe můžete vynutit, aby se příkazový řádek vrátil. V okně příkazového řádku pak můžete provádět další operace. Pro ukončení profilování použijte možnost **/shutdown** v samostatném příkazu **VSPerfASPNETCmd** .

Postup při zahájení profilace:

**VSPerfASPNETCmd** [ */Options*] **/nowait** _websiteUrl_

Ukončení profilace:

**VSPerfASPNETCmd/Shutdown** *websiteUrl*

## <a name="additional-options"></a>Další možnosti

K příkazům uvedeným dříve v této části můžete přidat kteroukoli z následujících možností s výjimkou příkazu **VSPerfASPNETCmd/Shutdown** .

|Možnost|Popis|
|------------|-----------------|
|**/Output:** `VspFile`|Ve výchozím nastavení jsou data profilace (. v aktuálním adresáři se vytvoří soubor *VSP* s názvem souboru **PerformanceReport. vsp**. Pomocí možnosti/Output zadejte jiné umístění, název souboru nebo obojí.|
|**/PackSymbols:Off**|Ve výchozím nastavení VsPerfASPNETCmd vloží symboly (funkce a názvy parametrů atd.) do. soubor *VSP* . Vložení symbolů může vytvořit soubor dat profilace velmi velký. Pokud budete mít přístup k. soubory *PDB* , které obsahují symboly při analýze dat, pomocí možnosti/packsymbols: off zakažte vkládání symbolů.|

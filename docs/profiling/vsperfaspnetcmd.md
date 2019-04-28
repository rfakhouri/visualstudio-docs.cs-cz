---
title: Příkaz VSPerfASPNetCmd | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
ms.assetid: f9e9f895-57bb-41e8-8bd1-cdaa738ec220
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3a6415734a1ea161c7baea26d2abde6d5390ce12
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62581184"
---
# <a name="vsperfaspnetcmd"></a>VSPerfASPNetCmd
**VSPerfASPNetCmd.exe** nástroj příkazového řádku vám umožní profilu technologie ASP.Net webové servery bez nutnosti nastavit proměnné prostředí nebo restartovat počítač. Použití **VSPerfASPNetCmd.exe** místo [VSPerfCmd](../profiling/vsperfcmd.md) Pokud profilujete webů ASP.NET a není nutné další funkce poskytovaná modulem **VSPerfCmd**. Další informace o **VSPerfASPNetCmd**, naleznete v tématu [profilace pohotová webových stránek pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md). **Příkaz VSPerfASPNetCmd** je upřednostňovaný příkazového řádku nástroje pro použití při použití samostatného profileru Profilovat webu ASP.NET.

## <a name="syntax"></a>Syntaxe
 **vsperfaspnetcmd** [/*Options*] *Website*

## <a name="options"></a>Možnosti

|Možnost|Popis|
|------------|-----------------|
|**/ Ukázkové** nebo **/s**|Profily webu pomocí metody vzorkování. **/ Ukázkové** je výchozí metodou. / Ukázkové nelze použít s **/Trace**.|
|**/ Trasování** nebo **/t**|Profily webu pomocí metody instrumentace. / Trasování nelze použít s **/Sample**.|
|**Či na disku paměti**[**:**`Type`] nebo **/m**[**:**{**a**&#124;**l**}]|Profily přidělení paměti a volitelně profily správu životnosti objektů (uvolnění paměti). **/ Paměti** jde použít s vzorkování nebo metody instrumentace.<br /><br /> *Typ* může být jedna z následujících akcí:<br /><br /> -   **přidělení** (nebo **a**) shromažďuje jenom data přidělení paměti.<br />-   **Doba života** (nebo **l**) shromažďuje data o přidělování a objekt životním cyklu paměti.<br /><br /> Výchozí hodnota `Type` je **přidělení**.|
|**/ Tip** nebo **/i**|Přidá podrobné žádosti ASP.NET a informace o volání ADO.NET data profilace. **/ Tip** jde použít s vzorkování nebo instrumentace metody a je možné s **Memory** možnost.|
|**/ Output:** `File` nebo   **/o:**`File`|Určuje cestu a název souboru dat profilování (. *Vsp*) soubor.|
|**/ NoWait** nebo **/n**|Vrátí příkaz výzva okamžitě tak, aby další příkazy lze použít v okně příkazového řádku. Je nutné zadat **příkaz VSPerfASPNETCmd/Shutdown** na samostatný příkazový řádek vypnout profilování.|
|**/PackSymbols**[:{**on**&#124;**off**}or   **/p**[:{**on**&#124;**off**}|Vloží symboly (názvy funkce a parametrů, atd.) v profilaci dat (. *Vsp*) soubor.|
|**/ Shutdown:** `Website`nebo   **/d:**`Website`|Zapne profilaci vypnout. Použijte parametr příkazového řádku po použití **/nowait** možnosti spuštění profilace, nebo pokud profiler neočekávaně ukončí. Zadejte stejnou adresu url, kterou jste použili v původním **VSPerfASPNETCmd** příkazu.|
|`Website`|Adresu url webu, který má být profilována.|

## <a name="see-also"></a>Viz také:
- [Pohotová profilace stránek pomocí VSPerfASPNETCmd webových](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)

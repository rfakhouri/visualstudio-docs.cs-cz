---
title: Příkaz VSPerfASPNetCmd | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
ms.assetid: f9e9f895-57bb-41e8-8bd1-cdaa738ec220
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9cb81f17abd1e7891dc3f78a85d6d1276991f070
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54762988"
---
# <a name="vsperfaspnetcmd"></a>VSPerfASPNetCmd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**VSPerfASPNetCmd.exe** nástroj příkazového řádku vám umožní do profilu webů ASP.Net bez nutnosti nastavit proměnné prostředí nebo restartovat počítač. Použití **VSPerfASPNetCmd.exe** místo [VSPerfCmd](../profiling/vsperfcmd.md) Pokud profilujete webů ASP.NET a není nutné další funkce poskytovaná modulem **VSPerCmd**. Další informace o **VSPerfASPNetCmd**, naleznete v tématu [rychlé webových profilů stránek pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md). **Příkaz VSPerfASPNetCmd** je upřednostňovaný příkazového řádku nástroje pro použití při použití samostatného profileru Profilovat webu technologie ASP.NET.  
  
## <a name="syntax"></a>Syntaxe  
 **vsperfaspnetcmd** [/*Options*] *Website*  
  
## <a name="options"></a>Možnosti  
  
|Možnost|Popis|  
|------------|-----------------|  
|**/ Ukázkové** nebo **/s**|Profily webu pomocí metody vzorkování. **/ Ukázkové** je výchozí metodou. / Ukázkové nelze použít s **/Trace**.|  
|**/ Trasování** nebo **/t**|Profily webu pomocí metody instrumentace. / Trasování nelze použít s **/Sample**.|  
|**Či na disku paměti**[**:**`Type`] nebo **/m**[**:**{**a**&#124;**l**}]|Profily přidělení paměti a volitelně profily správu životnosti objektů (uvolnění paměti). **/ Paměti** jde použít s vzorkování nebo metody instrumentace.<br /><br /> *Typ* může být jedna z následujících akcí:<br /><br /> -   **přidělení** (nebo **a**) shromažďuje jenom data přidělení paměti.<br />-   **Doba života** (nebo **l**) shromažďuje data o přidělování a objekt životním cyklu paměti.<br /><br /> Výchozí hodnota `Type` je **přidělení**.|  
|**/ Tip** nebo **/i**|Přidá podrobné žádosti ASP.NET a informace o volání ADO.NET data profilace. **/ Tip** jde použít s vzorkování nebo instrumentace metody a je možné s **Memory** možnost.|  
|**/ Output:** `File` nebo   **/o:**`File`|Určuje název a cesta k souboru souboru dat profilování (.vsp).|  
|**/ NoWait** nebo **/n**|Vrátí příkaz výzva okamžitě tak, aby další příkazy lze použít v okně příkazového řádku. Je nutné zadat **příkaz VSPerfASPNETCmd/Shutdown** na samostatný příkazový řádek vypnout profilování.|  
|**/PackSymbols**[:{**on**&#124;**off**}or   **/p**[:{**on**&#124;**off**}|Vloží symboly (názvy funkce a parametrů, atd.) v Profilování (.vsp) datový soubor.|  
|**/ Shutdown:** `Website`nebo   **/d:**`Website`|Zapne profilaci vypnout. Použijte parametr příkazového řádku po použití **/nowait** možnosti spuštění profilace, nebo pokud profiler neočekávaně ukončí. Zadejte stejnou adresu url, kterou jste použili v původním **VSPerfASPNETCmd** příkazu.|  
|`Website`|Adresu url webu, který má být profilována.|  
  
## <a name="see-also"></a>Viz také  
 [Pohotová profilace stránek pomocí VSPerfASPNETCmd webových](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)

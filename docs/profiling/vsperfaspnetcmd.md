---
title: VSPerfASPNetCmd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
ms.assetid: f9e9f895-57bb-41e8-8bd1-cdaa738ec220
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c6e4420b0466857177cad356de7bb4a737968f3
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="vsperfaspnetcmd"></a>VSPerfASPNetCmd
**VSPerfASPNetCmd.exe** nástroj příkazového řádku můžete do profilu webů ASP.Net bez nutnosti nastavení proměnných prostředí nebo restartovat počítač. Použití **VSPerfASPNetCmd.exe** místo [VSPerfCmd](../profiling/vsperfcmd.md) když jsou profilace webů ASP.NET a není nutné další funkce poskytované službou **VSPerfCmd**. Další informace o **VSPerfASPNetCmd**, najdete v části [profilace rychlé webové stránky pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md). **VSPerfASPNetCmd** je nástroj příkazového řádku upřednostňovaný používat při použití samostatných profileru profilu webu technologie ASP.NET.  
  
## <a name="syntax"></a>Syntaxe  
 **vsperfaspnetcmd** [/*možnosti*] *webu*  
  
## <a name="options"></a>Možnosti  
  
|Možnost|Popis|  
|------------|-----------------|  
|**/ Ukázku** nebo **/s**|Profily webu pomocí metody vzorkování. **/ Ukázku** je výchozí metodou. / Vzorové nelze použít s **/trasování**.|  
|**/ Trasování** nebo **/t**|Profily webu pomocí metody instrumentace. / Trasování nelze použít s **/ukázkové**.|  
|**Či na disku paměti**[**:**`Type`] nebo **/m**[**:**{**a**&#124;**l**}]|Profily přidělování paměti a volitelně profily životnosti objektů (uvolňování paměti). **Či na disku paměti** lze použít s vzorkuje nebo metody instrumentace.<br /><br /> *Typ* může být jedna z následujících akcí:<br /><br /> -   **přidělení** (nebo **a**) shromažďuje jenom data přidělení paměti.<br />-   **Doba platnosti** (nebo **l**) shromažďuje data o přidělení a objekt životnost paměti.<br /><br /> Výchozí hodnota `Type` je **přidělení**.|  
|**/ Tip** nebo **/i**|Přidá podrobné žádost ASP.NET a informace o volání ADO.NET data profilování. **/ Tip** lze použít s vzorkuje nebo metody instrumentace a dá použít s **/Memory** možnost.|  
|**/ Výstup:** `File` nebo   **/o:**`File`|Určuje název a cesta k souboru profilování souboru dat (.vsp).|  
|**/ NoWait** nebo   **/n**|Vrátí příkaz výzva okamžitě, aby v okně příkazového řádku můžete použít další příkazy. Musíte zadat **/VSPerfASPNETCmd Shutdown** na samostatném řádku příkaz k vypnutí profilace.|  
|**/ PackSymbols**[: {**na**&#124;**vypnout**} nebo **/p**[: {**na**&#124;**vypnout**}|Vloží symboly (názvy funkce a parametr atd.) v profilaci soubor dat (.vsp).|  
|**Nebo vypnutí:** `Website`nebo   **/d:**`Website`|Profilace vypněte oplátku. Použít jako jedinou možností na příkazovém řádku po použití **/nowait** možnost spustit profilování, nebo pokud neočekávaně ukončí profileru. Zadejte stejnou adresu url, který jste použili v původním **VSPerfASPNETCmd** příkaz.|  
|`Website`|Adresa url webu, který má být profilovaným.|  
  
## <a name="see-also"></a>Viz také  
 [Rychlé profilování webových stránek pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)

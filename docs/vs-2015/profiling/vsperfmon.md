---
title: VSPerfMon | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- VSPerfMon tool
- command line, tools
- command-line tools, VSPerfMon tool
- data [Visual Studio ALM], VSPerfMon tool
- performance data, VSPerfMon tool
- performance tools, VSPerfMon tool
- profilng tools,VSPerfCmd
ms.assetid: 37052afb-7a58-441f-bb17-f1587cc57068
caps.latest.revision: 35
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4a06a6632d62f853eef33cad00ad766e0d1aab87
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54776050"
---
# <a name="vsperfmon"></a>VSPerfMon
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vsperfmon – nástroj můžete použít ke shromažďování dat výkonu aplikace. Obvykle je tento nástroj pro spouštěn VSPerfCmd.exe. Vsperfmon – zobrazí informace o procesu připojení nebo odpojení, která není k dispozici s použitím nástroje VSPerfCmd. Chcete-li zobrazit tyto informace, začněte VSPerfMon v samostatném okně. K vyvolání vsperfmon – použijte následující syntaxi:  
  
```  
VSPerfMon [/U] </TRACE [/COUNTER:cfg] | /SAMPLE | /COVERAGE> /CROSSSESSION /OUTPUT <file name> [/WINCOUNTER:cfg] [/USER [DOMAIN\]username]  
```  
  
 Následující tabulka popisuje možnosti vsperfmon – nástroj:  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**U**|Přesměrovaný výstup konzoly je zapsán jako Unicode.  Toto musí být zadána první možnost.|  
|**VÝSTUP:** `<` *název souboru* `>`|Přesměruje výstup do zadaného názvu souboru.|  
|**TRASOVÁNÍ**|Spustí monitorování výkonu pro instrumentovanou profilaci.|  
|**UKÁZKA**|Spustí monitorování výkonu pro profilaci vzorkování.|  
|**POKRYTÍ**|Spustí monitorování výkonu pro shromažďování pokrytí kódu.|  
|**SOUBĚŽNOST**|Spustí monitor výkonu profilace kolize prostředků.|  
|**UŽIVATEL:** `[` *domény* `\]` *uživatelské jméno*|Umožňuje přístup klienta k monitorování výkonu ze zadaného účtu.|  
|**CROSSSESSION**|Umožňuje profilování mezi relacemi.|  
|**ČÍTAČ** `:cfg`|Když se používá metoda profilace instrumentace (trasování), určuje čítačů procesoru, které se mají shromažďovat u každého bodu instrumentace. Můžete shromažďovat více dat čítače zadáním více možností čítače.<br /><br /> Použijte následující syntaxi pro určení čítač (*cfg*) dat:<br /><br /> **Hodnota counterName** [**, znovu načíst**[,**FriendlyName**]]<br /><br /> -   **Hodnota counterName** je název čítače vrácená příkazem VSPerfCmd/querycounters.<br />-   **Znovu načíst** je interval vzorkování čítače událostí. Nepoužívejte *Reload* pomocí metody instrumentace.<br />-Li zadána, **FriendlyName** nahradí **CounterName** v nástrojích pro profilaci sestavy názvy sloupců.|  
|**WINCOUNTER** `:path`|Určuje čítač výkonu Windows zahrnout s daty značky. `path` je řetězec čítače výkonu Windows ve formátu cesty čítače PDH. Příklad:<br /><br /> \Processor(0)\\čas procesoru v %<br /><br /> \System\Context switches/sec|  
|**AUTOMARK** `:n`|Určuje časový interval (v milisekundách) automatického vkládání značek při použití /WINCOUNTER. Zaokrouhlena nejbližší 500ms.<br /><br /> Použijte 0 pro vypnutí automatického vkládání značek. (výchozí = 500 MS, je-li tento parametr zadán)|  
  
## <a name="see-also"></a>Viz také  
 [VSInstr](../profiling/vsinstr.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [VSPerfReport](../profiling/vsperfreport.md)   
 [Zobrazení sestav výkonu](../profiling/performance-report-views.md)

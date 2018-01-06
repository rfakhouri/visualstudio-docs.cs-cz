---
title: LineOff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76082063-20ef-47ae-ad64-81b43b654865
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ebab610e9f684cf55054fae6916e6d1b1fb40d67
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="lineoff"></a>LineOff
Ve výchozím nastavení profileru shromažďuje zdrojový kód řádku číslo a řádku číslo posunutí data při použití metoda profilování se vzorkováním. VSPerfCmd **LineOff** možnost zakáže shromažďování dat číslo řádku, pokud je VSPerfCmd se používá ke spuštění aplikace. Profilace data se shromažďují funkce úrovni při **LineOff** je zadán.  
  
 Můžete použít **LineOff** pouze s **spusťte** možnost, a pouze když profileru byl inicializován pro vzorkování pomocí **spustit**:**ukázka** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Launch:AppName /LineOff [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="required-options"></a>Požadované možnosti  
 **LineOff** možnost lze použít pouze na příkazový řádek, který obsahuje **spusťte** možnost.  
  
 **Spuštění:**`AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody vzorkování.  
  
## <a name="example"></a>Příklad  
 Tento příkaz spustí aplikace a profileru a zakáže vzorkování na úrovni řádku.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /LineOff  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
---
title: "Uvolňování paměti (VSPerfCmd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6a57cb824ca6c2ec4b2f52a070ae407690f83d69
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="gc-vsperfcmd"></a>Uvolňování paměti (VSPerfCmd)
**GC** možnost povoluje shromažďování rozhraní .NET Framework paměti přidělení a objekt životnosti. **GC** možnost lze použít pouze s metoda profilování se vzorkováním a jenom **spusťte** možnost.  
  
 Při použití **GC** možnost, vsperfclrenv – **/sampleon** příkaz se nevyžaduje.  
  
 Pokud nejsou zadány žádné parametry, nebo pokud **přidělení** je zadán parametr, jsou shromažďovány pouze rozhraní .NET Framework data přidělení paměti. Pokud **životnost** je zadán parametr, přidělení paměti rozhraní .NET Framework a rozhraní .NET Framework objektu životnost data jsou shromažďována.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 **Přidělení**  
 Výchozí hodnota. Shromažďuje údaje o přidělení paměti rozhraní .NET Framework.  
  
 **Doba platnosti**  
 Shromažďuje údaje o přidělení paměti rozhraní .NET Framework a životnosti objektů rozhraní .NET Framework.  
  
## <a name="required-options"></a>Požadované možnosti  
 **GC** možnost lze použít pouze s **spusťte** možnost.  
  
 **Spuštění:**`AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody vzorkování.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu spustí aplikaci a shromažďuje data přidělení paměti rozhraní .NET Framework.  
  
```  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
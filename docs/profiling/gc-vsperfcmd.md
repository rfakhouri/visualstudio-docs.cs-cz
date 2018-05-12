---
title: Uvolňování paměti (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08c9de6d307b54829e2f0783cf0ff272f399de68
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="gc-vsperfcmd"></a>Uvolňování paměti (VSPerfCmd)
**GC** možnost povoluje shromažďování rozhraní .NET Framework paměti přidělení a objekt životnosti. **GC** možnost lze použít pouze s metoda profilování se vzorkováním a jenom **spusťte** možnost.  
  
 Při použití **GC** možnost, vsperfclrenv – **/sampleon** příkaz se nevyžaduje.  
  
 Pokud nejsou zadány žádné parametry, nebo pokud **přidělení** je zadán parametr, jsou shromažďovány pouze rozhraní .NET Framework data přidělení paměti. Pokud **životnost** je zadán parametr, přidělení paměti rozhraní .NET Framework a rozhraní .NET Framework objektu životnost data jsou shromažďována.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 **Přidělení**  
 Výchozí hodnota. Shromažďuje údaje o přidělení paměti rozhraní .NET Framework.  
  
 **Doba platnosti**  
 Shromažďuje údaje o přidělení paměti rozhraní .NET Framework a životnosti objektů rozhraní .NET Framework.  
  
## <a name="required-options"></a>Požadované možnosti  
 **GC** možnost lze použít pouze s **spusťte** možnost.  
  
 **Spusťte:** `AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody vzorkování.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu spustí aplikaci a shromažďuje data přidělení paměti rozhraní .NET Framework.  
  
```cmd  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
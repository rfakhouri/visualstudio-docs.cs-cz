---
title: Args | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 20c35949-1f29-4282-ac75-4e6c237d71bc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40de97d134f24832c56b0cda7b8462a3f8f8c937
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53845535"
---
# <a name="args"></a>Args
VSPerfCmd.exe **Args** určuje seznam argumentů, které se předají k cílové aplikaci z **spuštění** podpříkaz.  
  
 **Args** jde použít jenom při **spuštění** je také zadán v příkazovém řádku. **Args** je volitelný při **spuštění** určena.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /Args:Arguments [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Arguments`  
 Seznam argumentů k cílové aplikaci z **spuštění** příkazu.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Spuštění:** `AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody odběru vzorků.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu **Args** možnost předat argumenty do TestApp.exe.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Args:"123, 'Hello World'"  
```  
  
## <a name="see-also"></a>Viz také:  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET.](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
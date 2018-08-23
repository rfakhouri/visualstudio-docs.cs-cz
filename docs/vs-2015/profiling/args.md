---
title: Args | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20c35949-1f29-4282-ac75-4e6c237d71bc
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4092a0f75808942eabf170a10f4dcec0836ca337
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627473"
---
# <a name="args"></a>Args
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Args](https://docs.microsoft.com/visualstudio/profiling/args).  
  
VSPerfCmd.exe **Args** určuje seznam argumentů, které se předají k cílové aplikaci z **spuštění** podpříkaz.  
  
 **Args** jde použít jenom při **spuštění** je také zadán v příkazovém řádku. **Args** je volitelný při **spuštění** určena.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Args:"123, 'Hello World'"  
```  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)




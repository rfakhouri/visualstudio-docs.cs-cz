---
title: "Argumentů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20c35949-1f29-4282-ac75-4e6c237d71bc
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 13243c0f7d0553b386d1a890e4d2be0272e9a27a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="args"></a>Args
VSPerfCmd.exe **argumentů** možnost určuje seznam argumentů, které se budou předávat na cíl aplikaci **spusťte** dílčí příkaz.  
  
 **Argumentů** lze použít pouze při **spusťte** rovněž je zadán v příkazovém řádku. **Argumentů** je volitelný při **spusťte** je zadán.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Launch:AppName /Args:Arguments [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Arguments`  
 Seznam argumentů na cílové aplikaci **spusťte** příkaz.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Spuštění:**`AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody vzorkování.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá **argumentů** možnost předání argumentů do TestApp.exe.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Args:"123, 'Hello World'"  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
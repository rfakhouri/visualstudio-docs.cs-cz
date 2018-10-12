---
title: AutoMark | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ee6e4beafb21ed7f7695c88fceb8516d5677cdb
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49259250"
---
# <a name="automark"></a>AutoMark
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**AutoMark** parametr určuje počet milisekund mezi kolekce událostí čítače výkonu Windows software. Čítače výkonu Windows jsou určené v **WinCounter** možnost.  
  
 Pouze jeden **AutoMark** možnost lze zadat na příkazovém řádku. Všimněte si, že **WinCounter** určený interval vzorkování **AutoMark** je nezávislá hlavní vzorkovací frekvence.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Parametry  
 `Milliseconds`  
 Určuje počet milisekund mezi kolekce událostí čítače výkonu Windows.  
  
## <a name="required-options"></a>Požadované možnosti  
 **WinCounter:** `Path`  
 Určuje název čítače výkonu Windows shromažďování. Při použití metody instrumentace je možné zadat více čítačů Windows. Při použití metody vzorkování lze zadat pouze jeden čítač softwaru. **WinCounter** možnost musí být zadána v příkazovém řádku, který obsahuje **Start** možnost.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu je interval vzorkování na 1000 milisekund nastavena pro dva čítače výkonu Windows.  
  
```  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)




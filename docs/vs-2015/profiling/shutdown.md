---
title: Vypnutí | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e7e351050859a96ca95c267bdcbe34ee19e7f87f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668180"
---
# <a name="shutdown"></a>Vypnutí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vypnutí](https://docs.microsoft.com/visualstudio/profiling/shutdown).  
  
**Vypnutí** možnost čeká všechny aktuálně profilovaný proces ukončit nebo odpojit, a pak profiler vypne a uzavře soubor dat profilování. **Vypnutí** možnost musí být poslední příkaz profilování.  
  
 Pokud není zadán parametr časového limitu, **vypnutí** možnost bude čekat bez omezení. Pokud je zadán parametr časového limitu, vrátí se možnost po zadaném počtu sekund bez vypnutí profileru a zavření souboru dat.  
  
 **Vypnutí** možnost musí být zadán v příkazovém řádku jedinou možností.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Timeout`  
 -   (Volitelné) Je-li zadán, vrátí možnost po zadaném počtu sekund bez vypnutí profileru a zavření souboru dat profilování.  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)




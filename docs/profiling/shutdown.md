---
title: Vypnutí | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 435011200065f1f27ff54c14c57d71eb651fd8e8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53952070"
---
# <a name="shutdown"></a>Vypnutí
**Vypnutí** možnost čeká všechny aktuálně profilovaný proces ukončit nebo odpojit, a pak profiler vypne a uzavře soubor dat profilování. **Vypnutí** možnost musí být poslední příkaz profilování.  
  
 Pokud není zadán parametr časového limitu, **vypnutí** možnost čekat po neomezenou dobu. Pokud je zadán parametr časového limitu, vrátí se možnost po zadaném počtu sekund bez vypnutí profileru a zavření souboru dat.  
  
 **Vypnutí** možnost musí být zadán v příkazovém řádku jedinou možností.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Timeout`  
 -   (Volitelné) Je-li zadán, vrátí možnost po zadaném počtu sekund bez vypnutí profileru a zavření souboru dat profilování.  
  
## <a name="see-also"></a>Viz také:  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)
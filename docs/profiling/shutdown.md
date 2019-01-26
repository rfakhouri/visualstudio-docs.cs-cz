---
title: Vypnutí | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 045f84542334b16d7e3d57fb48099e61f144cadd
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54992331"
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
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)
---
title: Vypnutí | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c835894d18ca1aea33f26f234a4df914114089c
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="shutdown"></a>Vypnutí
**Vypnutí** možnost čeká pro všechny aktuálně profilovaným proces ukončit nebo odpojit, a poté vypne profileru a ukončení profilování datového souboru. **Vypnutí** možnost musí být poslední příkaz z profilace spustit.  
  
 Pokud není zadán parametr časového limitu, **vypnutí** možnost čeká neomezenou dobu zaseknout. Pokud je zadán parametr časový limit, vrátí se možnost po zadaném počtu sekund bez vypnutí profileru nebo zavírání datového souboru.  
  
 **Vypnutí** možnost musí být pouze možnost zadat na příkazovém řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Timeout`  
 -   (Volitelné) -Li zadána, vrátí se možnost po zadaném počtu sekund bez vypnutí profileru nebo zavírání datového souboru profilování.  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
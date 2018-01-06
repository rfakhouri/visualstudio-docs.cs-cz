---
title: "Vypnutí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f2e5411a4d5b88340105f71248ca2e5c2410ff12
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="shutdown"></a>Vypnutí
**Vypnutí** možnost čeká pro všechny aktuálně profilovaným proces ukončit nebo odpojit, a poté vypne profileru a ukončení profilování datového souboru. **Vypnutí** možnost musí být poslední příkaz z profilace spustit.  
  
 Pokud není zadán parametr časového limitu, **vypnutí** možnost vyčká po neomezenou dobu. Pokud je zadán parametr časový limit, vrátí se možnost po zadaném počtu sekund bez profileru vypnutí nebo zavírání datového souboru.  
  
 **Vypnutí** možnost musí být pouze možnost zadat na příkazovém řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Timeout`  
 -   (Volitelné) -Li zadána, vrátí se možnost po zadaném počtu sekund bez profileru vypnutí nebo zavírání datového souboru profilování.  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
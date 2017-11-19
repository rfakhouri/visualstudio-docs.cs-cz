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
ms.openlocfilehash: 822d9a15a248a72c19d41d548dcb68092c43d268
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
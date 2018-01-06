---
title: "Výstup | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b7452ad6aa8d7f190eebbc35d4be087c14dcd51a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="output"></a>Výstup
**Výstup** možnost určuje název datového souboru profilace pro výkonnostní relace. **Výstup** musí být použit s **spustit** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `FileName`  
 Název datového souboru. Úplné a částečné cesty, jsou přijaty. Pokud cesta není zadána, soubor je vytvořen v aktuálním adresáři.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Výstup** možnost se musí použít s **spustit** možnost.  
  
 **Začátek:**`Method`  
 Určuje název výstupního souboru.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu je profilování datový soubor vytvoří v aktuálním adresáři.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
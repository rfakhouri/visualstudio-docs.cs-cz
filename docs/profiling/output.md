---
title: Výstup | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 06d8518e6ea5e5cc4dbfbe3ae51d9fb1b06757a5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
  
 **Spusťte:** `Method`  
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
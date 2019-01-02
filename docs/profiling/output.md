---
title: Výstup | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4bca95dea2ac381d28d2c2a4043f94dcfb6fd6e9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53922250"
---
# <a name="output"></a>Výstup
**Výstup** Určuje název souboru dat profilování pro relaci výkonu. **Výstup** musí být použit s **Start** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `FileName`  
 Název datového souboru. Jsou přijímány úplné a částečné cesty. Pokud cesta není zadaná, soubor se vytvoří v aktuálním adresáři.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Výstup** možnost musí být použita s **Start** možnost.  
  
 **Spusťte:** `Method`  
 Určuje název výstupního souboru.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu je vytvořen soubor dat profilování v aktuálním adresáři.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
```  
  
## <a name="see-also"></a>Viz také:  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)
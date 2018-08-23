---
title: Výstup | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d08942b36fedab1f5c5535619bcb6c520093ff9b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680811"
---
# <a name="output"></a>Výstup
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [výstup](https://docs.microsoft.com/visualstudio/profiling/output).  
  
**Výstup** Určuje název souboru dat profilování pro relaci výkonu. **Výstup** musí být použit s **Start** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
```  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)




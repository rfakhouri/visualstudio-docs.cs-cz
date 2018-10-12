---
title: Uživatel (VSPerfCmd) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee1a478e-374d-4f30-ae28-d260b9d4723a
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b390852c94477a6b02d43b0dbc7678384c622ced
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49301997"
---
# <a name="user-vsperfcmd"></a>Uživatel (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**Uživatele** Určuje doménu a uživatelské jméno účtu vlastnícího profilovaný proces. Tato možnost je vyžadována, pouze pokud je proces spuštěn pod jiným než přihlášeným uživatelem. Vlastník procesu je uvedena ve sloupci uživatelské jméno na záložce procesy ve Správci úloh Windows.  
  
 **Uživatele** možnost lze zadat pouze na příkazovém řádku, který také obsahuje **Start** možnost možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName /User:[Domain\]UserName [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Domain`  
 Název domény uživatele.  
  
 `UserName`  
 Jméno uživatele.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Uživatele** možnost se dá použít jenom s **Start** možnost.  
  
 **Spusťte:** `Method`  
 Inicializuje možnost profileru zadané metodě profilování.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **uživatele** možnost.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /User:SYSTEM  
```  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)




---
title: CrossSession | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 196107019a43f8f76beeb55cde6a56034375b9d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="crosssession"></a>CrossSession
VSPerfCmd.exe **CrossSession** možnost umožňuje profileru ke shromažďování dat z jakékoli relace konzoly. **CrossSession** možnost se musí použít s **spustit** možnost.  
  
 Můžete použít zkratku **CS** místě **CrossSession**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /CrossSession [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="valid-options"></a>Platné možnosti.  
 Povolte profilování v jiné relaci, **CrossSession** s musí být Zadaná možnost **spustit** možnost. **CrossSession** musí být zadaná také v žádném následné **VSPerfCmd připojit** a **odpojení** příkazy.  
  
 **Začátek:**`Method`  
 **Spustit** možnost inicializuje profileru pro zadanou metodu profilování.  
  
 **Připojení:** *PID*[**,***PID*]  
 Zahájí profilace zadaný procesy.  
  
 **Odpojení**[**:***PID*[,*PID*]]  
 Zastaví profilace zadaný procesy.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu **CrossSession** možnost se používá k připojení k aplikaci, která byla spuštěna v jiné relaci konzoly.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession  
VSPerfCmd.exe /Attach:12345 /CS  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
---
title: CrossSession | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d0f9ef3577f1285f428415de6b5b452d2a4cd7b6
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2018
---
# <a name="crosssession"></a>CrossSession
VSPerfCmd.exe **CrossSession** možnost umožňuje profileru ke shromažďování dat z jakékoli relace konzoly. **CrossSession** možnost se musí použít s **spustit** možnost.  
  
 Můžete použít zkratku **CS** místě **CrossSession**.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Start:Method /CrossSession [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="valid-options"></a>Platné možnosti.  
 Povolte profilování v jiné relaci, **CrossSession** s musí být Zadaná možnost **spustit** možnost. **CrossSession** musí být zadaná také v žádném následné **VSPerfCmd připojit** a **odpojení** příkazy.  
  
 **Spusťte:** `Method`  
 **Spustit** možnost inicializuje profileru pro zadanou metodu profilování.  
  
 **Připojení:** *PID*[**, *** PID*]  
 Zahájí profilace zadaný procesy.  
  
 **Odpojení**[**: *** PID*[,*PID*]]  
 Zastaví profilace zadaný procesy.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu **CrossSession** možnost se používá k připojení k aplikaci, která byla spuštěna v jiné relaci konzoly.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession  
VSPerfCmd.exe /Attach:12345 /CS  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
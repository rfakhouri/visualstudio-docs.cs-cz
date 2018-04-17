---
title: TargetCLR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64c87f53de999a65294a6bb388e7a90420dc6cd1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="targetclr"></a>TargetCLR
**TargetCLR** možnost určuje verzi běžné language runtime (CLR) do profilu při načtení více než jedna verze modulu CLR v aplikaci.  
  
 Ve výchozím nastavení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci cíle první verzi modulu CLR zavedená aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>Parametry  
 `ClrVersion`  
 Číslo verze modulu CLR. Použijte formát verze **vN.N.NNNNN**.  
  
## <a name="required-options"></a>Požadované možnosti  
 **TargetCLR** možnost lze použít pouze s **spusťte** nebo **Attach** možnosti.  
  
 **Spusťte:** `AppName`  
 Zadaná aplikace spustí a začne profil.  
  
 **Připojení:** `PID`  
 Spustí proces zadaný profil.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu se používá možnost TargetCLR a ujistěte se, že je profilovaným 4.0.11003 verze modulu CLR.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```
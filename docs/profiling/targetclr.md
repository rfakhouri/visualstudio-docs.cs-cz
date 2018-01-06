---
title: TargetCLR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a69edb2730ff89a50dd45252258fc57e7205de3d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
 **Spuštění:**`AppName`  
 Zadaná aplikace spustí a začne profil.  
  
 **Připojení:**`PID`  
 Spustí proces zadaný profil.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu se používá možnost TargetCLR a ujistěte se, že je profilovaným 4.0.11003 verze modulu CLR.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```
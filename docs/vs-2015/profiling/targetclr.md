---
title: TargetCLR | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 915ca4a859b4c80f785262f1c05698c4d34a683b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629714"
---
# <a name="targetclr"></a>TargetCLR
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [TargetCLR](https://docs.microsoft.com/visualstudio/profiling/targetclr).  
  
**TargetCLR** Určuje verzi common language runtime (CLR) do profilu je do aplikace načtena více než jedna verze modulu CLR.  
  
 Ve výchozím nastavení [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů pro profilaci sady cílit na první verzi modulu CLR, který je načten aplikací.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>Parametry  
 `ClrVersion`  
 Číslo verze modulu CLR. Použijte formát verze **vN.N.NNNNN**.  
  
## <a name="required-options"></a>Požadované možnosti  
 **TargetCLR** možnost se dá použít jenom s **spuštění** nebo **připojit** možnosti.  
  
 **Spuštění:** `AppName`  
 Zadaná aplikace spustí a začne profilu.  
  
 **Připojení:** `PID`  
 Spuštění profilu určeného procesu.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu se používá možnost TargetCLR abyste měli jistotu, že je modul CLR verze 4.0.11003 profilována.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```




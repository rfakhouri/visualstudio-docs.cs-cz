---
title: TargetCLR | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1e4ca52f631b3e2de9c01daab7e6268c42f20268
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54801193"
---
# <a name="targetclr"></a>TargetCLR
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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

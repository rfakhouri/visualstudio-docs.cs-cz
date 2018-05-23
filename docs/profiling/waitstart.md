---
title: WaitStart | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e9845a9814f70afd18fddb880c8e51804964161
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="waitstart"></a>WaitStart
Možnost WaitStart způsobí, že se VSPerfCmd.exe počáteční dílčí příkaz vrátí jenom v případě, že byla inicializována profileru nebo po zadaném počtu sekund byla úspěšná. Ve výchozím nastavení vrátí příkaz ke spuštění okamžitě. Pokud nebyl zadán profileru vrátí dílčí příkaz ke spuštění, je vrácena chyba. Pokud není zadaný počet sekund, příkaz ke spuštění čeká neomezenou dobu zaseknout.  
  
 Možnost WaitStart je užitečná v dávkových souborech zajistit, že tento profileru byl inicializován.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Seconds`  
 Počet sekund pro čekání před návratem od dílčí příkaz ke spuštění.  
  
## <a name="required-options"></a>Požadované možnosti  
 Možnost WaitStart lze použít pouze s dílčí příkaz ke spuštění.  
  
 **Výstup:** `filename`  
 Určuje název výstupního souboru.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 V tomto příkladu souboru batch příkaz ke spuštění bude počkejte 5 sekund kvůli profileru k chybě při inicializaci.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```
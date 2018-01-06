---
title: WaitStart | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2e7fc09c29c0aa5ca708953b1c8aa3e008c06c38
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="waitstart"></a>WaitStart
Možnost WaitStart způsobí, že se VSPerfCmd.exe počáteční dílčí příkaz vrátí jenom v případě, že byla inicializována profileru nebo po zadaném počtu sekund byla úspěšná. Ve výchozím nastavení vrátí příkaz ke spuštění okamžitě. Pokud nebyl zadán profileru vrátí dílčí příkaz ke spuštění, je vrácena chyba. Pokud není zadaný počet sekund, příkaz ke spuštění čeká neomezenou dobu zaseknout.  
  
 Možnost WaitStart je užitečná v dávkových souborech zajistit, že tento profileru byl inicializován.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Seconds`  
 Počet sekund pro čekání před návratem od dílčí příkaz ke spuštění.  
  
## <a name="required-options"></a>Požadované možnosti  
 Možnost WaitStart lze použít pouze s dílčí příkaz ke spuštění.  
  
 **Výstup:**`filename`  
 Určuje název výstupního souboru.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 V tomto příkladu souboru batch příkaz ke spuštění bude počkejte 5 sekund kvůli profileru k chybě při inicializaci.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```
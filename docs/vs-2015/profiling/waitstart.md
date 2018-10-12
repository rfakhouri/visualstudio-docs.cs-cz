---
title: WaitStart | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9f111ae1aed079f0c0cc0d94a1d1da7c8557e76
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49285906"
---
# <a name="waitstart"></a>WaitStart
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Možnost WaitStart způsobí, že dílčí příkaz VSPerfCmd.exe Start vrátit pouze v případě, že profiler byl inicializován nebo po uplynutí zadaném počtu sekund. Ve výchozím nastavení, Start příkaz vrátí hodnotu okamžitě. Vrátí dílčí příkaz Start bez inicializace okna profilování, vrátí se chyba. Pokud není zadaný počet sekund, po neomezenou dobu čeká příkazu Start.  
  
 WaitStart možnost je užitečná v dávkových souborech a zajistit, že profiler byl inicializován.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Seconds`  
 Počet sekund čekání před návratem z dílčích příkazu Start.  
  
## <a name="required-options"></a>Požadované možnosti  
 Možnost WaitStart jde použít jenom s dílčího příkazu Start.  
  
 **Výstup:** `filename`  
 Určuje název výstupního souboru.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 V tomto příkladu soubor batch příkazu Start. Počkejte 5 sekund kvůli na inicializaci profileru.  
  
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




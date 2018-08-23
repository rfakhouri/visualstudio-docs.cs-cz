---
title: DebugBreak a __debugbreak | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DebugBreak
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], DebugBreak function
- DebugBreak function
- breakpoints, DebugBreak function
ms.assetid: 9787c795-df94-4f48-bc8d-3bf899b67421
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 005490038b293dbb644ec99ca2fbeaa77c0eb2c9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675043"
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak a __debugbreak
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [DebugBreak a __debugbreak](https://docs.microsoft.com/visualstudio/debugger/debugbreak-and-debugbreak).  
  
Můžete volat funkci DebugBreak Win32 nebo [__debugbreak](http://msdn.microsoft.com/library/1d1e1c0c-891a-4613-ae4b-d790094ba830) vnitřní v libovolném bodě v kódu. `DebugBreak` a `__debugbreak` má stejný účinek jako nastavení zarážky na tomto místě.  
  
 Protože `DebugBreak` je volání funkce systému, musí být nainstalován symboly, informace v zásobníku správné volání se zobrazí po přerušení ladění systému. V opačném případě informace v zásobníku volání zobrazené ladicím programem mohou být vypnout jeden snímek. Pokud používáte `__debugbreak`, symboly nejsou požadovány.  
  
## <a name="see-also"></a>Viz také  
 [Vnitřní funkce kompilátoru](http://msdn.microsoft.com/library/48bb9929-7d78-4fd8-a092-ae3c9f971858)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Zadání symbolu (.pdb) a zdrojové soubory](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)




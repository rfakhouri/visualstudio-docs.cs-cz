---
title: DebugBreak a __debugbreak | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DebugBreak
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], DebugBreak function
- DebugBreak function
- breakpoints, DebugBreak function
ms.assetid: 9787c795-df94-4f48-bc8d-3bf899b67421
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cb05c054ffc5dd273b532f72afe0ca046adbe606
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55041721"
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak a __debugbreak
Můžete volat funkci DebugBreak Win32 nebo [__debugbreak](/cpp/intrinsics/debugbreak) vnitřní v libovolném bodě v kódu. `DebugBreak` a `__debugbreak` má stejný účinek jako nastavení zarážky na tomto místě.  
  
 Protože `DebugBreak` je volání funkce systému, musí být nainstalován symboly, informace v zásobníku správné volání se zobrazí po přerušení ladění systému. V opačném případě informace v zásobníku volání zobrazené ladicím programem mohou být vypnout jeden snímek. Pokud používáte `__debugbreak`, symboly nejsou požadovány.  
  
## <a name="see-also"></a>Viz také  
 [Vnitřní funkce kompilátoru](/cpp/intrinsics/compiler-intrinsics)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
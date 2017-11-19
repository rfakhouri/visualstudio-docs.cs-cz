---
title: "Debugbreak – a __debugbreak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DebugBreak
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
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1763c117ce9cdb815f12213830079136169b2c35
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak a __debugbreak
Můžete volat funkci debugbreak – Win32 nebo [__debugbreak –](/cpp/intrinsics/debugbreak) vnitřní v libovolném bodě v kódu. `DebugBreak`a `__debugbreak` mají stejný účinek jako nastavení boru přerušení v tomto umístění.  
  
 Protože `DebugBreak` je volání funkce systému, ladění systému symboly musí být nainstalován zajistit správné volání informace zásobníku se zobrazí po ukončování řádků. Jinak hodnota zásobníku volání informace zobrazí ladicí program může být vypnuto jeden snímek. Pokud používáte `__debugbreak`, symboly nejsou povinné.  
  
## <a name="see-also"></a>Viz také  
 [Vnitřní funkce kompilátoru](/cpp/intrinsics/compiler-intrinsics)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
---
title: "Jak zjistím, že moje ukazatele poškodily adresu paměti? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 863acbf45268330e106360dd7778acab94b670de
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Jak zjistím, že moje ukazatele poškodily adresu paměti?
## <a name="problem-description"></a>Popis problému  
 Myslím, že jeden z mých ukazatelů může být poškozování paměti na adrese 0x00408000. Jak můžete najít na co se děje existuje?  
  
## <a name="solution"></a>Řešení  
  
#### <a name="check-for-heap-corruption"></a>Zkontrolujte poškození haldy  
  
-   Většina poškození paměti je ve skutečnosti kvůli poškození haldy. Zkuste použít globální příznaky nástroj, (gflags.exe) nebo pageheap.exe. V tématu [http://support.microsoft.com/default.aspx?scid=kb;en-us;286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470).  
  
#### <a name="to-find-where-the-memory-address-is-modified"></a>Pokud chcete najít, kde je adresa paměti změnit  
  
1.  Nastavte zarážky data na 0x00408000. V tématu [zarážku změn dat (pouze nativní C++)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus_only).  
  
2.  Při kliknutí na zarážce, použijte **paměti** okno zobrazení paměti obsah počínaje 0x00408000. Další informace najdete v tématu [paměti Windows](../debugger/memory-windows.md).  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
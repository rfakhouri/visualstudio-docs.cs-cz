---
title: Jak zjistím, že moje ukazatele poškodily adresu paměti? | Dokumenty Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c9d3a6c754aa200703c5f2a0ed2e458e08830a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674243"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Jak zjistím, že moje ukazatele poškodily adresu paměti?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Jak zjistím If Moje ukazatele poškozeno adresu paměti?](https://docs.microsoft.com/visualstudio/debugger/how-can-i-find-out-if-my-pointers-corrupt-a-memory-address-q).  
  
Popis problému  
 Myslím, že jeden z mých ukazatelů může způsobovat poškození paměti na adrese 0x00408000. Jak zjistím, co se děje?  
  
## <a name="solution"></a>Řešení  
  
#### <a name="check-for-heap-corruption"></a>Vyhledejte poškození haldy  
  
-   Většina poškození paměti je vlastně způsobena poškozením haldy. Zkuste použít Global Flags Utility, (gflags.exe) nebo pageheap.exe. Zobrazit [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470).  
  
#### <a name="to-find-where-the-memory-address-is-modified"></a>Chcete-li najít, kde byla změněna adresa paměti  
  
1.  Nastavte zarážku data na 0x00408000. Zobrazit [nastavit zarážku změny dat (pouze nativní C++)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus_only).  
  
2.  Až se dostanete k zarážce, použijte **paměti** obsah okna paměti začínající na 0x00408000. Další informace najdete v tématu [paměti Windows](../debugger/memory-windows.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)




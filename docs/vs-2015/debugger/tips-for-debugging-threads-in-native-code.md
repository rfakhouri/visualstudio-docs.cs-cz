---
title: Tipy k ladění vláken v nativním kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
caps.latest.revision: 25
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4a0a72f9846add13f2f57581a0b836a9f57f8150
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54756811"
---
# <a name="tips-for-debugging-threads-in-native-code"></a>Tipy k ladění vláken v nativním kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zde je několik tipů, které můžete využít při ladění vláken v nativním kódu:  
  
-   Obsah bloku vláken informace můžete zobrazit zadáním `@TIB` v **Watch** okno nebo **QuickWatch** dialogové okno.  
  
-   Kód poslední chyby pro aktuální vlákno můžete zobrazit tak, že zadáte `@Err` v **Watch** okno nebo **QuickWatch** dialogové okno.  
  
-   Funkce knihovny Run-Time C (CRT) mohou být užitečné při ladění aplikace s více vlákny. Další informace najdete v tématu [_malloc_dbg](http://msdn.microsoft.com/library/c97eca51-140b-4461-8bd2-28965b49ecdb).  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)

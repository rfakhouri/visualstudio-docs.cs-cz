---
title: "Tipy k ladění vláken v nativním kódu | Microsoft Docs"
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
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b0a2df03fdcb32e09824e37c26587912c542dea
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="tips-for-debugging-threads-in-native-code"></a>Tipy k ladění vláken v nativním kódu
Zde jsou některé tipy, které můžete použít při ladění vláken v nativním kódu:  
  
-   Obsah bloku vláken informace můžete zobrazit zadáním `@TIB` v **sledovat** okno nebo **QuickWatch** dialogové okno.  
  
-   Kód poslední chyby pro aktuální vlákno můžete zobrazit zadáním `@Err` v **sledovat** okno nebo **QuickWatch** dialogové okno.  
  
-   Funkce běhové knihovny jazyka C (CRT) může být užitečná pro ladění vícevláknové aplikace. Další informace najdete v tématu [_malloc_dbg –](/cpp/c-runtime-library/reference/malloc-dbg).  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
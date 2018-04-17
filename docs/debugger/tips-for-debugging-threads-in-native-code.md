---
title: Tipy k ladění vláken v nativním kódu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 72b913c64d78966bde96419978a066cc9921ebaa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="tips-for-debugging-threads-in-native-code"></a>Tipy k ladění vláken v nativním kódu
Zde jsou některé tipy, které můžete použít při ladění vláken v nativním kódu:  
  
-   Obsah bloku vláken informace můžete zobrazit zadáním `@TIB` v **sledovat** okno nebo **QuickWatch** dialogové okno.  
  
-   Kód poslední chyby pro aktuální vlákno můžete zobrazit zadáním `@Err` v **sledovat** okno nebo **QuickWatch** dialogové okno.  
  
-   Funkce běhové knihovny jazyka C (CRT) může být užitečná pro ladění vícevláknové aplikace. Další informace najdete v tématu [_malloc_dbg –](/cpp/c-runtime-library/reference/malloc-dbg).  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
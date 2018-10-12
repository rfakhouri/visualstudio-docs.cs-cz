---
title: Tipy k ladění vláken v nativním kódu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
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
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06e8690583794c23ce95fb52ef6cab3ab6667afe
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49184922"
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




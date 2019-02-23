---
title: Tipy k ladění vláken v nativním kódu | Dokumentace Microsoftu
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 8f76a6ea66396a8c5780731945cad87eab94b8ee
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717595"
---
# <a name="tips-for-debugging-threads-in-native-code"></a>Tipy k ladění vláken v nativním kódu
Zde je několik tipů, které můžete využít při ladění vláken v nativním kódu:

-   Obsah bloku vláken informace můžete zobrazit zadáním `@TIB` v **Watch** okno nebo **QuickWatch** dialogové okno.

-   Kód poslední chyby pro aktuální vlákno můžete zobrazit tak, že zadáte `@Err` v **Watch** okno nebo **QuickWatch** dialogové okno.

-   Funkce knihovny Run-Time C (CRT) mohou být užitečné při ladění aplikace s více vlákny. Další informace najdete v tématu [_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg).

## <a name="see-also"></a>Viz také
- [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)
- [Ladění nativního kódu](../debugger/debugging-native-code.md)
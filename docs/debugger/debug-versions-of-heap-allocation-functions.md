---
title: "Ladění verzí funkcí přidělení haldy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.crt
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- debugging [CRT], heap allocation functions
- debugging memory leaks, CRT debug library functions
- malloc function
- memory leaks, CRT debug library functions
- heap allocation, debug
- _malloc_dbg function
ms.assetid: 91748bdc-f4cd-4d8b-ab98-0493dab7ed0d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 63642402f6e98e42b2d4954a6065f61fb61159b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="debug-versions-of-heap-allocation-functions"></a>Ladění verzí funkcí přidělení haldy
Běhové knihovny jazyka C obsahuje speciální ladění verzí funkcí přidělení haldy. Tyto funkce mají stejné názvy jako vydání verze _dbg připojí k nim. Toto téma popisuje rozdíly mezi prodejní verze funkce CRT a verze _dbg pomocí `malloc` a `_malloc_dbg` jako příklady.  
  
 Když [_DEBUG –](/cpp/c-runtime-library/debug) je definován, CRT mapuje všechny [malloc –](/cpp/c-runtime-library/reference/malloc) volání [_malloc_dbg –](/cpp/c-runtime-library/reference/malloc-dbg). Proto není potřeba přepisu kódu pomocí `_malloc_dbg` místo `malloc` získat výhody při ladění.  
  
 Můžete chtít volání `_malloc_dbg` explicitně, ale. Volání metody `_malloc_dbg` explicitně má některé další výhody:  
  
-   Sledování `_CLIENT_BLOCK` zadejte přidělení.  
  
-   Ukládání souborů a řádku číslo zdrojového kde požadavek na přidělení došlo k chybě.  
  
 Pokud nechcete převést vaše `malloc` volání `_malloc_dbg`, můžete získat informace o zdrojovém souboru tak, že definujete [_crtdbg_map_alloc –](/cpp/c-runtime-library/crtdbg-map-alloc), což způsobí, že preprocesoru přímo na mapě všechna volání `malloc` k `_malloc_dbg` aniž byste museli spoléhat na obálku kolem `malloc`.  
  
 Ke sledování samostatných typy přidělování v blocích klienta, musí volat `_malloc_dbg` přímo a nastavte `blockType` parametru `_CLIENT_BLOCK`.  
  
 Když není definován _DEBUG –, volání `malloc` nejsou narušen, volání `_malloc_dbg` překládána na `malloc`, definice [_crtdbg_map_alloc –](/cpp/c-runtime-library/crtdbg-map-alloc) ignorována a zdroje informací o souboru, která se týkají požadavek na přidělení není k dispozici. Protože `malloc` nemá parametr typ bloku, požadavky pro `_CLIENT_BLOCK` typy jsou považovány za standardní přidělení.  
  
## <a name="see-also"></a>Viz také  
 [Techniky ladění CRT](../debugger/crt-debugging-techniques.md)
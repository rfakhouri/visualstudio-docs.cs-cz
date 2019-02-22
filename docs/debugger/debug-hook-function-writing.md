---
title: Zápis funkce háku ladění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vc.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 82145d39adc519bfd1324cc36805cea7b97b1664
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56628920"
---
# <a name="debug-hook-function-writing"></a>Zápis funkce háku ladění
Tato část popisuje některé funkce háku ladění vlastní, můžete napsat a, které umožňují vložit kód do některé předdefinované body v normálním zpracování ladicího programu.

## <a name="in-this-section"></a>V tomto oddílu
 [Funkce háku bloku klienta](../debugger/client-block-hook-functions.md) poskytuje pokyny a vzor pro psaní funkcí, které sestavy dat uložených v blocích po _CLIENT_BLOCK obsah nebo ověření.

 [Funkce háku přidělení](../debugger/allocation-hook-functions.md) definuje funkci háku přidělení, zkoumá jeho použití různých, poukazuje na omezení a poskytuje prototypu.

 [Háky přidělení a přidělení paměti CRT](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md) popisuje omezení pro funkce háku přidělení explicitně ignorování `_CRT_BLOCK` zablokuje, pokud volání funkcí knihovny run-time jazyka C, které přidělit vnitřní paměti. Toto téma rovněž uvádí důsledky, pokud vaše háku přidělení neignoruje `_CRT_BLOCK` bloky (příklady) a jak změnit výchozí přidělení funkci, připojení **CrtDefaultAllocHook**.

 [Funkce háku sestavy](../debugger/report-hook-functions.md) popisuje `_CrtSetReportHook`, které můžete použít k filtrování sestavy a zaměřte se na konkrétní typy přidělení. Toto téma obsahuje také prototypu.

## <a name="related-sections"></a>Související oddíly

- [Techniky ladění CRT](../debugger/crt-debugging-techniques.md) – odkazy na ladění techniky pro knihovny Run-Time jazyka C, včetně použití ladění knihovny CRT, makra pro vytváření sestav, rozdíly mezi `malloc` a `_malloc_dbg`, zápis funkce háku ladění a CRT haldy ladění.
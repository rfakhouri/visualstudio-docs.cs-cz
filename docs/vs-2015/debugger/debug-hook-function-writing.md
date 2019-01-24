---
title: Zápis funkce háku ladění | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.hooks
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0554c1494bec757d1baecd78cdc302608e5b6b3e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54779937"
---
# <a name="debug-hook-function-writing"></a>Zápis funkce háku ladění
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato část popisuje některé funkce háku ladění vlastní, můžete napsat a, které umožňují vložit kód do některé předdefinované body v normálním zpracování ladicího programu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Funkce volání bloku klienta](../debugger/client-block-hook-functions.md)  
 Poskytuje pokyny a vzor pro psaní funkcí, které sestavy dat uložených v blocích po _CLIENT_BLOCK obsah nebo ověření.  
  
 [Funkce volání přidělení](../debugger/allocation-hook-functions.md)  
 Definuje funkci háku přidělení, zkoumá různé používá, body omezení a poskytuje prototypu.  
  
 [Háky přidělení a přidělení paměti CRT](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)  
 Popisuje omezení pro funkce háku přidělení explicitně ignorování `_CRT_BLOCK` zablokuje, pokud volání funkcí knihovny run-time jazyka C, které přidělit vnitřní paměti. Toto téma rovněž uvádí důsledky, pokud vaše háku přidělení neignoruje `_CRT_BLOCK` bloky (příklady) a jak změnit výchozí přidělení funkci, připojení **CrtDefaultAllocHook**.  
  
 [Funkce volání sestavy](../debugger/report-hook-functions.md)  
 Tento článek popisuje `_CrtSetReportHook`, které můžete použít k filtrování sestavy a zaměřte se na konkrétní typy přidělení. Toto téma obsahuje také prototypu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Techniky ladění CRT](../debugger/crt-debugging-techniques.md)  
 Odkazy na ladění techniky pro knihovny Run-Time jazyka C, včetně použití ladění knihovny CRT, makra pro vytváření sestav, rozdíly mezi `malloc` a `_malloc_dbg`, zápis funkce háku ladění a haldy ladění CRT.

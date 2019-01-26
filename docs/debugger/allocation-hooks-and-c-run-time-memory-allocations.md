---
title: Háky přidělení a přidělení běhové paměti jazyka C | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], hook functions
- memory allocation, troubleshooting allocation hooks
- allocation hooks
- hooks, allocation
ms.assetid: cc34ee96-3d91-41bd-a019-aa3759139e7e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f9432eab55f22bcf18266a10e4e1616997ed8c4a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54924175"
---
# <a name="allocation-hooks-and-c-run-time-memory-allocations"></a>Háky přidělení a přidělení běhové paměti jazyka C
Je velmi důležité omezení funkce háku přidělení, že se musí explicitně Ignorovat `_CRT_BLOCK` bloky. Tyto bloky jsou přidělení paměti provedené interně funkcemi knihovny run-time jazyka C, je-li využívají volání funkcí knihovny run-time jazyka C, které přidělit vnitřní paměti. Můžete ignorovat `_CRT_BLOCK` bloky zahrnutím následujícího kódu na začátku přidělení funkci připojení:  
  
```cpp
if ( nBlockUse == _CRT_BLOCK )  
    return( TRUE );  
```  
  
 Pokud vaše háku přidělení nebude ignorovat `_CRT_BLOCK` blokuje, pak všechny funkce knihovny run-time jazyka C v váš hook můžete zachytávat program v nekonečné smyčce. Například `printf` díky interní přidělení. Pokud váš kód hook volá `printf`, poté způsobí, že výsledný přidělení hook volat akci, která bude volat **printf** znovu, a tak dále, dokud přetečení zásobníku. Pokud potřebujete sestavy `_CRT_BLOCK` operace přiřazení jednu cestu pro obejití toto omezení je použít funkce rozhraní Windows API, nikoli funkcí jazyka C za běhu, pro formátování a výstup. Vzhledem k tomu, že rozhraní API Windows nepoužívejte haldy knihovny run-time jazyka C, se nebude zachytávat vaše háku přidělení v nekonečné smyčce.  
  
 Když si zblízka zdrojové soubory knihovny run-time, uvidíte, že funkci, výchozí přidělení připojení **CrtDefaultAllocHook** (které jednoduše vrátí **TRUE**), se nachází v samostatném souboru své vlastní, DBGHOOK. C. Pokud chcete, aby vaše háku přidělení volat i pro přidělení provedených za běhu spouštěcí kód, který se spouští před vaší aplikace **hlavní** funkce, můžete nahradit výchozí funkci svůj vlastní místo pomocí [_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook).  
  
## <a name="see-also"></a>Viz také  
 [Zápis funkce volání pro ladění](../debugger/debug-hook-function-writing.md)   

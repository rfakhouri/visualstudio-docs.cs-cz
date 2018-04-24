---
title: Funkce háku přidělení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- memory allocation, logging allocation information
- insufficient memory
- debugging [C++], hook functions
- _CrtSetAllocHook function
- allocation hooks
- hooks, allocation
ms.assetid: 6bfbdb65-8cb1-4c21-8c45-7194a2b77c1e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c46b498ea36459dff0eb538ac3e0371fd9c5707
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="allocation-hook-functions"></a>Funkce háku přidělení
Funkce háku přidělení, nainstalovat pomocí [_crtsetallochook –](/cpp/c-runtime-library/reference/crtsetallochook), se nazývá pokaždé, když je paměti přidělené, znovu přidělený nebo vydání. Tento typ háku slouží k mnoha různým účelům. Použijte ho k testování, jak se aplikace zpracovává situacích, není dostatek paměti, například nebo chcete zjistit vzory přidělování nebo k protokolování informací o přidělení pro pozdější analýzu.  
  
> [!NOTE]
>  Mějte na paměti omezení týkající se použití funkce běhové knihovny jazyka C v funkci háku přidělení, popsané v [zachytí přidělení a přidělení paměti C Run-Time](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md).  
  
 Funkce háku přidělení musí mít prototyp takto:  
  
```  
int YourAllocHook(int nAllocType, void *pvData,  
        size_t nSize, int nBlockUse, long lRequest,  
        const unsigned char * szFileName, int nLine )  
```  
  
 Ukazatele, který můžete předat [_crtsetallochook –](/cpp/c-runtime-library/reference/crtsetallochook) je typu **_crt_alloc_hook –**, jak jsou definovány v CRTDBG. V:  
  
```  
typedef int (__cdecl * _CRT_ALLOC_HOOK)  
    (int, void *, size_t, int, long, const unsigned char *, int);  
```  
  
 Když běhové knihovny volá háku, *nAllocType* argument určuje, jaké přidělení operaci je třeba provést (**_HOOK_ALLOC**, **_HOOK_REALLOC**, nebo **_HOOK_FREE**). V případě bezplatný nebo opakované přidělení `pvData` obsahuje ukazatel na uživatele tématu bloku se uvolnit. V případě přidělení, tento ukazatel je však hodnotu null, protože ještě nedošlo k přidělení. Zbývající argumenty obsahovat velikost přidělení Nejistá, její typ bloku počet po sobě jdoucích žádosti přidružené a ukazatel na název a řádek číslo souboru ve kterém byl proveden přidělení, pokud je k dispozici. Po funkce háku provede ať analýzu a jiné úlohy jeho chce autora, musí vracet buď **TRUE**, což indikuje, že můžete pokračovat v operaci přidělení, nebo **FALSE**, která udává, operace by měla nezdaří. Jednoduché háku tohoto typu mohou Zkontrolujte množství paměti přidělené dosavadní a vrátí **FALSE** Pokud tato šířka malé překročení. Aplikace by prostředí poté druh chyby přidělení, které by obvykle dochází pouze v případě, že byl velmi málo dostupné paměti. Složitější háky může sledovat jednotlivé vzory přidělování, analýza využití paměti nebo sestavy, když dojde k konkrétních situacích.  
  
## <a name="see-also"></a>Viz také  
 [Háky přidělení a přidělení běhové paměti jazyka C](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)   
 [Zápis funkce háku ladění](../debugger/debug-hook-function-writing.md)   

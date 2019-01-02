---
title: Funkce háku bloku klienta | Dokumentace Microsoftu
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
- client blocks, validating and reporting data
- debugging [C++], hook functions
- _CrtSetDumpClient function
- client blocks, hook functions
- hooks, client block
ms.assetid: f21c197e-565d-4e3f-9b27-4c018c9b87fc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ef8beac3b2b9c837cb2e5ee18743c9c640aacc08
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53966573"
---
# <a name="client-block-hook-functions"></a>Funkce háku bloku klienta
Pokud chcete ověřit nebo sestavy obsah data uložená v `_CLIENT_BLOCK` zablokuje, můžete napsat funkci speciálně pro tento účel. Funkce, která zapíšete musí mít prototyp podobně jako následujícím, jak jsou definovány v CRTDBG. V:  

```cpp
void YourClientDump(void *, size_t)  
```  

 Jinými slovy, by měla přijímat funkce háku **void** ukazatel na začátku přidělení bloku, společně s **size_t** zadejte hodnotu, která udává velikost přidělení a vrátit `void`. Než jeho obsah, záleží na vás.  

 Po instalaci pomocí funkce háku [_CrtSetDumpClient](/cpp/c-runtime-library/reference/crtsetdumpclient), bude volána pokaždé, když `_CLIENT_BLOCK` zálohované bloku. Pak můžete použít [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype) informace o typu nebo podtypu vypsaná bitová kopie řidicího bloků.  

 Ukazatel na funkci, kterou předat `_CrtSetDumpClient` je typu **_crt_dump_client –**, jak jsou definovány v CRTDBG. V:  

```cpp
typedef void (__cdecl *_CRT_DUMP_CLIENT)  
   (void *, size_t);  
```  

## <a name="see-also"></a>Viz také  
 [Zápis funkce háku ladění](../debugger/debug-hook-function-writing.md)   
 [Ukázka crt_dbg2](https://msdn.microsoft.com/library/21e1346a-6a17-4f57-b275-c76813089167)   
 [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype)

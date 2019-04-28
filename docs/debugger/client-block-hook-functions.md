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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 900e8db238ee26e0a7015c2acc1741a1917c8cb3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62564070"
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

- [Zápis funkce volání pro ladění](../debugger/debug-hook-function-writing.md)
- [Ukázka crt_dbg2](https://msdn.microsoft.com/library/21e1346a-6a17-4f57-b275-c76813089167)
- [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype)
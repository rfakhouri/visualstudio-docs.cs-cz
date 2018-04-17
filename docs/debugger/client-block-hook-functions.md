---
title: Funkce háku bloku klienta | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 711f7de86617f6574427a65c6efcef62c558306b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="client-block-hook-functions"></a>Funkce háku bloku klienta
Pokud chcete ověřit nebo ohlásit obsah dat uložených v `_CLIENT_BLOCK` blokuje, můžete napsat funkci speciálně pro tento účel. Funkce, která můžete psát musí mít prototyp podobný následujícímu, jak jsou definovány v CRTDBG. V:  
  
```  
void YourClientDump(void *, size_t)  
  
```  
  
 Jinými slovy, musí přijmout funkce háku **void** ukazatel na začátku bloku přidělení, společně s **size_t –** zadejte hodnotu, která určuje velikost přidělení a vrátí `void`. Než tu, která její obsah se na vás.  
  
 Po instalaci pomocí funkce háku [_crtsetdumpclient –](/cpp/c-runtime-library/reference/crtsetdumpclient), bude zavolána pokaždé, když `_CLIENT_BLOCK` vypsána bloku. Pak můžete použít [_crtreportblocktype –](/cpp/c-runtime-library/reference/crtreportblocktype) informace o typu nebo podtypu dumpingových bloků.  
  
 Ukazatele na funkce, kterou předáte do `_CrtSetDumpClient` je typu **_crt_dump_client –**, jak jsou definovány v CRTDBG. V:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)  
   (void *, size_t);  
```  
  
## <a name="see-also"></a>Viz také  
 [Zápis funkce háku ladění](../debugger/debug-hook-function-writing.md)   
 [Ukázka crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)   
 [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype)
---
title: Funkce háku bloku klienta | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- client blocks, validating and reporting data
- debugging [C++], hook functions
- _CrtSetDumpClient function
- client blocks, hook functions
- hooks, client block
ms.assetid: f21c197e-565d-4e3f-9b27-4c018c9b87fc
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c5b1c754255ba0bc659c9b6968ad8ba0dea629ec
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65702328"
---
# <a name="client-block-hook-functions"></a>Funkce háku bloku klienta
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud chcete ověřit nebo sestavy obsah data uložená v `_CLIENT_BLOCK` zablokuje, můžete napsat funkci speciálně pro tento účel. Funkce, která zapíšete musí mít prototyp podobně jako následujícím, jak jsou definovány v CRTDBG. V:  
  
```  
void YourClientDump(void *, size_t)  
  
```  
  
 Jinými slovy, by měla přijímat funkce háku **void** ukazatel na začátku přidělení bloku, společně s **size_t** zadejte hodnotu, která udává velikost přidělení a vrátit `void`. Než jeho obsah, záleží na vás.  
  
 Po instalaci pomocí funkce háku [_CrtSetDumpClient](https://msdn.microsoft.com/library/f3dd06d0-c331-4a12-b68d-25378d112033), bude volána pokaždé, když `_CLIENT_BLOCK` zálohované bloku. Pak můžete použít [_CrtReportBlockType](https://msdn.microsoft.com/library/0f4b9da7-bebb-4956-9541-b2581640ec6b) informace o typu nebo podtypu vypsaná bitová kopie řidicího bloků.  
  
 Ukazatel na funkci, kterou předat `_CrtSetDumpClient` je typu **_crt_dump_client –**, jak jsou definovány v CRTDBG. V:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)  
   (void *, size_t);  
```  
  
## <a name="see-also"></a>Viz také  
 [Zápis funkce háku ladění](../debugger/debug-hook-function-writing.md)   
 [Ukázka crt_dbg2](https://msdn.microsoft.com/21e1346a-6a17-4f57-b275-c76813089167)   
 [_CrtReportBlockType](https://msdn.microsoft.com/library/0f4b9da7-bebb-4956-9541-b2581640ec6b)

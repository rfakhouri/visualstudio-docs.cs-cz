---
title: Funkce háku bloku klienta | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29bbfb24566a59047e47090f92a040c3c2fe8a12
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669229"
---
# <a name="client-block-hook-functions"></a>Funkce háku bloku klienta
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [funkce háku bloku klienta](https://docs.microsoft.com/visualstudio/debugger/client-block-hook-functions).  
  
Pokud chcete ověřit nebo sestavy obsah data uložená v `_CLIENT_BLOCK` zablokuje, můžete napsat funkci speciálně pro tento účel. Funkce, která zapíšete musí mít prototyp podobně jako následujícím, jak jsou definovány v CRTDBG. V:  
  
```  
void YourClientDump(void *, size_t)  
  
```  
  
 Jinými slovy, by měla přijímat funkce háku **void** ukazatel na začátku přidělení bloku, společně s **size_t** zadejte hodnotu, která udává velikost přidělení a vrátit `void`. Než jeho obsah, záleží na vás.  
  
 Po instalaci pomocí funkce háku [_CrtSetDumpClient](http://msdn.microsoft.com/library/f3dd06d0-c331-4a12-b68d-25378d112033), bude volána pokaždé, když `_CLIENT_BLOCK` zálohované bloku. Pak můžete použít [_CrtReportBlockType](http://msdn.microsoft.com/library/0f4b9da7-bebb-4956-9541-b2581640ec6b) informace o typu nebo podtypu vypsaná bitová kopie řidicího bloků.  
  
 Ukazatel na funkci, kterou předat `_CrtSetDumpClient` je typu **_crt_dump_client –**, jak jsou definovány v CRTDBG. V:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)  
   (void *, size_t);  
```  
  
## <a name="see-also"></a>Viz také  
 [Zápis funkce háku ladění](../debugger/debug-hook-function-writing.md)   
 [Ukázka crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)   
 [_CrtReportBlockType](http://msdn.microsoft.com/library/0f4b9da7-bebb-4956-9541-b2581640ec6b)




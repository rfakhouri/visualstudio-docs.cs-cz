---
title: Idialoadcallback2::restrictdbgaccess – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2::RestrictDBGAccess method
ms.assetid: 63b67a93-2910-4fff-aa70-6b2eaa08e5c8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1dfbcee715ff1407eb74940e7a63e47c1625e423
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idialoadcallback2restrictdbgaccess"></a>IDiaLoadCallback2::RestrictDBGAccess
Určuje, jestli hledáte informace o ladění je povolené z soubory dbg.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT RestrictDBGAccess();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Žádné jiné než vrátit hodnotu `S_OK` aby hledáte informace o ladění z soubory dbg.  
  
## <a name="see-also"></a>Viz také  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)
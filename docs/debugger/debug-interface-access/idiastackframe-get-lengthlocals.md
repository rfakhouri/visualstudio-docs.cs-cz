---
title: Idiastackframe::get_lengthlocals – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_lengthLocals method
ms.assetid: dbc3e544-578a-4f0b-8d20-f21ad4cbb604
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bfe821ea0cc0e2258377218046464441c5b9cd7b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31460319"
---
# <a name="idiastackframegetlengthlocals"></a>IDiaStackFrame::get_lengthLocals
Získá počet bajtů lokální proměnné nabídnutých v zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_lengthLocals (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí počet bajtů lokální proměnné.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
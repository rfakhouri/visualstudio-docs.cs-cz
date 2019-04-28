---
title: Struktura JS_NATIVE_FRAME | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JS_NATIVE_FRAME
apilocation:
- jscript9diag.dll
ms.assetid: 5afa2ee1-b3e2-47cb-b304-84f96e6fbb14
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a0777cf42b9ed9412602cb34ed2d521deca1fb9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62968669"
---
# <a name="jsnativeframe-structure"></a>Struktura JS_NATIVE_FRAME
Představuje rámec zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct {  
    UINT64 InstructionOffset;    UINT64 ReturnOffset;    UINT64 FrameOffset;    UINT64 StackOffset;  
} JS_NATIVE_FRAME;  
```  
  
## <a name="members"></a>Členové  
 `InstructionOffset`  
 Ukazatele na instrukci.  
  
 `ReturnOffset`  
 Zpáteční adresa.  
  
 `FrameOffset`  
 Ukazatel na rámec.  
  
 `StackOffset`  
 Ukazatel zásobníku.  
  
## <a name="remarks"></a>Poznámky  
 `JS_NATIVE_FRAME` Struktura používá `IJsStackFrameEnumerator`.  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)
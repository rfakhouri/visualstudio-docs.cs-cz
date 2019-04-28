---
title: Debugstackframedescriptor – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DebugStackFrameDescriptor
apilocation:
- scrobj.dll
helpviewer_keywords:
- DebugStackFrameDescriptor structure
ms.assetid: a86bcb99-41e4-4a26-a1dd-e1458fb73139
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fddae48178ec6c56ce647f5c4f3a1bff3d81a980
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955191"
---
# <a name="debugstackframedescriptor-structure"></a>Struktura DebugStackFrameDescriptor
Vytváří výčet rámců zásobníku a slučuje výstup z několika enumerátorů ve stejném vláknu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct tagDebugStackFrameDescriptor {  
   IDebugStackFrame *pdsf;  
   DWORD_PTR        dwMin;  
   DWORD_PTR        dwLim;  
   BOOL             fFinal;  
   IUnknown         *punkFinal;  
} DebugStackFrameDescriptor;  
```  
  
## <a name="members"></a>Členové  
 `pdsf`  
 Orámovat objekt zásobníku.  
  
 `dwMin`  
 Vyjádření závislé na počítači nižší řadu fyzické adresy přidružené k tento rámec zásobníku.  
  
 `dwLim`  
 Závislé na počítači reprezentuje horní hranice fyzických adres spojených s Tento rámec zásobníku.  
  
 `fFinal`  
 Příznak, který označuje, že rámec je právě zpracovává.  
  
 `punkFinal`  
 Pokud tento parametr není `NULL`má být spuštěn nový, a aktuální enumerátor sloučení by se měla zastavit. Objekt určuje, jak spustit nový výčet.  
  
## <a name="remarks"></a>Poznámky  
 Správce ladění procesu používá tuto strukturu řazení zásobníku z několika skriptovacích strojů. Podle konvence zásobníky růst dolů. V důsledku toho na architekturách, kde zásobníky růst, adresy by měl být doplněny párech.  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)
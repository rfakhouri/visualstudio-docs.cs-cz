---
title: Debugstackframedescriptor – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: c50c717cad626f4caf634c6a83b2af7213b78f83
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088475"
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
---
title: IDebugExceptionEvent2::PassToDebuggee | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExceptionEvent2::PassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::PassToDebuggee
ms.assetid: a20d0f0b-2ca0-4437-bd22-9213c81d2738
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 338127784a7ea4ee474edf1bfc58a75c5df7704d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53945610"
---
# <a name="idebugexceptionevent2passtodebuggee"></a>IDebugExceptionEvent2::PassToDebuggee
Určuje, zda výjimky by měly být předány program laděn při provádění pokračuje, nebo pokud by měl být zahozeny výjimku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT PassToDebuggee(  
   BOOL fPass  
);  
```  
  
```csharp  
int PassToDebuggee(  
   int fPass  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `fPass`  
 [in] Nenulová (`TRUE`) Pokud výjimky by měly být předány program laděn při provádění pokračuje nebo nula (`FALSE`) Pokud výjimky by měl být zahozeny.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Voláním této metody nezpůsobí skutečně jakýkoli kód, který se spustí v programu, který se právě ladí. Volání je pouze se nastavit stav pro další spuštění kódu. Například volání [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) metoda může vrátit `S_OK` s [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md).`dwState` pole nastaveno `EXCEPTION_STOP_SECOND_CHANCE`.  
  
 Rozhraní IDE se může zobrazit [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) událostí a volání [pokračovat](../../../extensibility/debugger/reference/idebugprogram2-continue.md) metody. Ladicí stroj (DE) by měly mít výchozí chování pro zpracování v případě, pokud `PassToDebuggee` metoda není volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)   
 [Continue](../../../extensibility/debugger/reference/idebugprogram2-continue.md)
---
title: IDebugExceptionEvent2::CanPassToDebuggee | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExceptionEvent2::CanPassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::CanPassToDebuggee
ms.assetid: ae4bbe0a-fbe1-49be-a310-ea64279a434b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6c4b0112c972c5521abc1007ad98259fae145769
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53822807"
---
# <a name="idebugexceptionevent2canpasstodebuggee"></a>IDebugExceptionEvent2::CanPassToDebuggee
Určuje, zda ladicí stroj (DE) podporuje možnost k laděnému při provádění pokračuje programu předat tuto výjimku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CanPassToDebuggee(  
   void  
);  
```  
  
```csharp  
int CanPassToDebuggee();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí buď `S_OK` (výjimky může být předán program) nebo `S_FALSE` (výjimky nelze předat).  
  
## <a name="remarks"></a>Poznámky  
 DE musí mít výchozí akci k předání do laděného procesu. Rozhraní IDE se může zobrazit [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) událostí a volání [pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md) metody bez volání `CanPassToDebuggee` metody. Proto je DE by měl mít výchozí případ pro předávání výjimku, nebo ne.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [Continue](../../../extensibility/debugger/reference/idebugprocess3-continue.md)
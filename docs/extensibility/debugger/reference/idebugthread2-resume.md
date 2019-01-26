---
title: IDebugThread2::Resume | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugThread2::Resume
helpviewer_keywords:
- IDebugThread2::Resume
ms.assetid: 36aad682-b0b9-40a2-b3fc-f0e61d41cdbc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 807f89eeed4e85e86c1a09a34ae12744bac8e0ae
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935264"
---
# <a name="idebugthread2resume"></a>IDebugThread2::Resume
Pokračuje v provádění vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Resume (   
   DWORD *pdwSuspendCount  
);  
```  
  
```csharp  
int Resume (   
   out uint pdwSuspendCount  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwSuspendCount`  
 [out] Vrátí počet pozastavení po operaci obnovení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každé volání této metody sníží počet potlačení dokud nedosáhne 0 na dobu, ve skutečnosti pokračování provádění. Zobrazí se tento počet pozastavení v **vlákna** okno ladění.  
  
 Pro každé volání této metody musí být předchozí volání [pozastavit](../../../extensibility/debugger/reference/idebugthread2-suspend.md) metody. Počet potlačení Určuje, kolikrát `IDebugThread2::Suspend` dosud byla volána metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md)
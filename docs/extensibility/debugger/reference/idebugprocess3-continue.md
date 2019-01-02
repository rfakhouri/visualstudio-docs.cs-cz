---
title: IDebugProcess3::Continue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::Continue
helpviewer_keywords:
- IDebugProcess3::Continue
ms.assetid: 57506242-5763-4c08-adb9-8a78ce02cebb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4c417998ab9c73ae2b52e297caa9de3dc9874f69
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53947696"
---
# <a name="idebugprocess3continue"></a>IDebugProcess3::Continue
Se bude spouštět dál tento proces v zastaveném stavu. Všechny předchozí stav spuštění (například krok) se zachová, a proces začne provádět znovu.  
  
> [!NOTE]
>  Tato metoda by měla být použita místo [pokračovat](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Continue(  
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Continue(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt představující vláknu pokračovat.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána k tomuto procesu bez ohledu na to, kolik procesy nejsou laděny nebo který proces vygeneruje událostí ukončení. Implementaci musí zachovat předchozí stav provádění (například krok) a pokračovat v provádění, jako by měl nikdy zastavila před dokončením předchozích spuštění. To znamená, pokud vlákno v tento proces dělal překročení operace a byla zastavena, protože nějaký jiný proces zastavená a potom `Continue` byla volána, zadané vlákno musí dokončit původní překročení.  
  
 **Upozornění** Neodesílat událostí ukončení nebo okamžité (synchronní) události, která [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování tohoto volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
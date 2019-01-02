---
title: IDebugProgram2::Step | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Step
helpviewer_keywords:
- IDebugProgram2::Step
ms.assetid: e4c2ffce-9810-4088-8162-eac9ef04f2a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 861c9ba2c6266294f5da9f6cd03ea9e85971e07d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53950456"
---
# <a name="idebugprogram2step"></a>IDebugProgram2::Step
Provádí se krok.  
  
> [!NOTE]
>  Tato metoda je zastaralá. Použití [krok](../../../extensibility/debugger/reference/idebugprocess3-step.md) metoda místo.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Step(   
   IDebugThread2*  pThread,  
   STEPKIND        sk,  
   STEPUNIT        step  
);  
```  
  
```csharp  
int Step(   
   IDebugThread2  pThread,  
   enum_STEPKIND  sk,  
   enum_STEPUNIT  step  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vlákna se stupňovitým.  
  
 `sk`  
 [in] Hodnota z [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) výčet, který určuje typ kroku.  
  
 `step`  
 [in] Hodnota z [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) výčet, který určuje jednotku kroku (třeba pomocí příkazu nebo instrukce).  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V případě, že je komunikace mezi vlákny ani synchronizaci vláken, by se spustit ostatní vlákna v program při krokování konkrétní vlákno.  
  
> [!WARNING]
>  Neodesílat událostí ukončení nebo okamžité (synchronní) události, která [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování tohoto volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
helpviewer_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 63d6550dd462e9d0c43d79064700440732e75d12
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960864"
---
# <a name="idebugengineprogram2watchforexpressionevaluationonthread"></a>IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
Umožňuje nebo zakazuje vyhodnocení výrazu, ke kterým došlo u dané vlákno, i v případě, že program přestal.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT WatchForExpressionEvaluationOnThread(   
   IDebugProgram2*       pOriginatingProgram,  
   DWORD                 dwTid,  
   DWORD                 dwEvalFlags,  
   IDebugEventCallback2* pExprCallback,  
   BOOL                  fWatch  
);  
```  
  
```csharp  
int WatchForExpressionEvaluationOnThread(   
   IDebugProgram2       pOriginatingProgram,  
   uint                  dwTid,  
   uint                  dwEvalFlags,  
   IDebugEventCallback2 pExprCallback,  
   int                   fWatch  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pOriginatingProgram`  
 [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt představující program, který je vyhodnocení výrazu.  
  
 `dwTid`  
 [in] Určuje identifikátor vlákna.  
  
 `dwEvalFlags`  
 [in] Kombinace příznaků z [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčet určující, jak se má provést vyhodnocení.  
  
 `pExprCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který se má použít k odeslání události ladění, ke kterým dochází při vyhodnocení výrazu.  
  
 `fWatch`  
 [in] Pokud nenulová (`TRUE`), umožňuje vyhodnocování výrazů ve vlákně identifikovaný `dwTid`; v opačném případě nula (`FALSE`) nepovoluje vyhodnocení výrazu v daném vláknu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když správce ladění relace (SDM) požádá program identifikován `pOriginatingProgram` parametr vyhodnocení výrazu, upozorní všech ostatních připojených programů po zavolání metody.  
  
 Vyhodnocení výrazu v jedné aplikaci může způsobit, že kód ke spuštění v jiném, z důvodu vyhodnocení funkce nebo vyhodnocení žádné `IDispatch` vlastnosti. Tato metoda umožňuje z tohoto důvodu vyhodnocení výrazu ke spuštění a dokončení, i když vlákno je pravděpodobně zastavená v rámci tohoto programu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
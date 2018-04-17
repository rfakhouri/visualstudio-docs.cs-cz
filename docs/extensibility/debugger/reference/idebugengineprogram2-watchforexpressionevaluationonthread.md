---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
helpviewer_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a3f89502beeb1e8165450c7c07f3f55f83dd39e1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugengineprogram2watchforexpressionevaluationonthread"></a>IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
Umožňuje (nebo zakáže) vyhodnocení výrazu proběhnout v daném vláknu i v případě, že program byla zastavena.  
  
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
 [v] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt reprezentující program, který je vyhodnocení výrazu.  
  
 `dwTid`  
 [v] Určuje identifikátor vlákno.  
  
 `dwEvalFlags`  
 [v] Kombinace příznaků z [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) výčet, který určit, jak má provést vyhodnocení.  
  
 `pExprCallback`  
 [v] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který chcete použít k odeslání ladění události, které nastaly během vyhodnocení výrazu.  
  
 `fWatch`  
 [v] Pokud nulová (`TRUE`), umožňuje vyhodnocení výrazu na vlákno identifikovaný `dwTid`, jinak hodnota nula (`FALSE`) zakáže vyhodnocení výrazu v daném vláknu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když správce ladicí relace (SDM) požádá program, identifikovaný `pOriginatingProgram` parametr k vyhodnocení výrazu, upozorní všech ostatních připojených programy voláním této metody.  
  
 Vyhodnocení výrazu v jednom programu může způsobit, že kód pro spuštění v jiném, z důvodu vyhodnocení funkce nebo vyhodnocení všech `IDispatch` vlastnosti. Z tohoto důvodu se tato metoda umožňuje vyhodnocení výrazu ke spuštění a dokončení, i když v tento program je pravděpodobně zastavená vlákno.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
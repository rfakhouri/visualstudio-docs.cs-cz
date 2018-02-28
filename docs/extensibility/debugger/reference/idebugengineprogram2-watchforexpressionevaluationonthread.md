---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
helpviewer_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e40af42d1dd639b80ffac3e2f3cf9c4501782b45
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
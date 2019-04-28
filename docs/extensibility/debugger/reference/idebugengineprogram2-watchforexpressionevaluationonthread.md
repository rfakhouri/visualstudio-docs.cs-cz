---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: 4c0572bfa8ebe1b70548483b17c58d08c8a0f9ca
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920377"
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
- [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)
- [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
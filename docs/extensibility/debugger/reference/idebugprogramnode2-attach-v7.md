---
title: IDebugProgramNode2::Attach_V7 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramNode2::Attach
helpviewer_keywords:
- IDebugProgramNode2::Attach_V7
- IDebugProgramNode2::Attach
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 42f269a62671864f3da2c0ca00c56a43a4ab9cba
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54975982"
---
# <a name="idebugprogramnode2attachv7"></a>IDebugProgramNode2::Attach_V7

> [!Note]
> ZASTARALÉ. NEPOUŽÍVEJTE.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Attach_V7 (
   IDebugProgram2*       pMDMProgram,
   IDebugEventCallback2* pCallback,
   DWORD                 dwReason
);
```

```csharp
int Attach_V7 (
   IDebugProgram2       pMDMProgram,
   IDebugEventCallback2 pCallback,
   uint                 dwReason
);
```

#### <a name="parameters"></a>Parametry

`pMDMProgram` [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, které představuje připojení k programu.

 `pCallback` [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) rozhraní použité k odesílání událostí ladění na SDM.

 `dwReason` [in] Hodnota z [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) výčet, který je obsažený důvod připojení.

## <a name="return-value"></a>Návratová hodnota

Implementace by měla vždy vrátit `E_NOTIMPL`.

## <a name="remarks"></a>Poznámky

> [!WARNING]
> Od verze Visual Studio 2005, tato metoda se už nepoužívá a by měl vždy vrátit `E_NOTIMPL`. Zobrazit [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) rozhraní alternativní způsob, pokud uzel program potřebuje k označení, nemůže být připojen k nebo pokud uzel programu je jednoduše nastavení program `GUID`. V opačném případě implementovat [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) metody.

## <a name="prior-to-visual-studio-2005"></a>Před Visual Studio 2005

Tato metoda musí být implementována pouze v případě, že je DE běží v adresním prostoru programu, který se právě ladí. Jinak tato metoda by měla vrátit `S_FALSE`.

Když tato metoda je volána, musíte odeslat DE [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) události objektu, pokud nebyl odeslán již pro tuto instanci [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) rozhraní, stejně jako [ IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) a [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) objekty událostí. [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) události objektu je potom odeslán, pokud `dwReason` parametr `ATTACH_REASON_LAUNCH`.

DE musí volat [GetProgramId](../../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) metodu [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt Poskytnutý [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) události objektu a uložit identifikátor GUID tohoto programu v instanci data `IDebugProgram2` implementované DE objektu.

## <a name="see-also"></a>Viz také

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)  
[IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)  
[Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)  
[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)  
[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)  
[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)  
[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
[IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)  
[IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)  
[ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)
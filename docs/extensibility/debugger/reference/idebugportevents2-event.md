---
title: IDebugPortEvents2::Event | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEvents2::Event
helpviewer_keywords:
- IDebugPortEvents2::Event
ms.assetid: 5cc813f7-04a1-4462-9ea7-fbddcf0e0143
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6ede9055f97a796e4e007914f68e370d4ff81420
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66326749"
---
# <a name="idebugportevents2event"></a>IDebugPortEvents2::Event
Tato metoda odesílá události, které místo vytváření a ničení procesy a programů na portu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Event(
   IDebugCoreServer2* pServer,
   IDebugPort2*       pPort,
   IDebugProcess2*    pProcess,
   IDebugProgram2*    pProgram,
   IDebugEvent2*      pEvent,
   REFIID             riidEvent
);
```

```csharp
int Event(
   IDebugCoreServer2 pServer,
   IDebugPort2       pPort,
   IDebugProcess2    pProcess,
   IDebugProgram2    pProgram,
   IDebugEvent2      pEvent,
   ref Guid          riidEvent
);
```

## <a name="parameters"></a>Parametry
`pMachine`\
[in] [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) objekt, který představuje server pro ladění (je jedna pro každou instanci [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]) ve kterém došlo k události.

`pPort`\
[in] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) objekt, který reprezentuje port, ve kterém došlo k události.

`pProcess`\
[in] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objekt, který představuje proces, ve kterém došlo k události.

`pProgram`\
[in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který reprezentuje program, ve kterém došlo k události.

`pEvent`\
[in] [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) objekt, který identifikuje událost. Možné události jsou následující:

- [IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)

- [IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)

- [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)

- [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)

`riidEvent`\
[in] Identifikátor GUID události. Protože události je přetypován na [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) před voláním této metody, tento identifikátor je snazší zjistit, která událost je odesíláno.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
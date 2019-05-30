---
title: IDebugProcess3::Execute | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::Execute
helpviewer_keywords:
- IDebugProcess3::Execute
ms.assetid: d831cd81-d7bf-4172-8517-aa699867791f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6b4b854c752bc7b1f66687074fbfe86286fc48fb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66314005"
---
# <a name="idebugprocess3execute"></a>IDebugProcess3::Execute
Se bude spouštět dál tento proces v zastaveném stavu. Vymazat všechny předchozí stav provádění (například krok) a proces začne provádět znovu.

> [!NOTE]
> Tato metoda by měla být použita místo [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md).

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Execute(
   IDebugThread2* pThread
);
```

```csharp
int Execute(
   IDebugThread2 pThread
);
```

## <a name="parameters"></a>Parametry
`pThread`\
[in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt představující spuštění vlákna.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Když uživatel spustí provádění z zastaven nějaký jiný proces na vlákno, tato metoda je volána k tomuto procesu. Tato metoda je volána, i když uživatel vybere **Start** příkaz **ladění** nabídky v integrovaném vývojovém prostředí. Implementace této metody může být stejně jednoduché jako volání funkce [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md) metodu na aktuální vlákno v procesu.

> [!WARNING]
> Neodesílat událostí ukončení nebo okamžité (synchronní) události, která [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování tohoto volání; v opačném případě ladicí program může přestat reagovat.

## <a name="see-also"></a>Viz také:
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
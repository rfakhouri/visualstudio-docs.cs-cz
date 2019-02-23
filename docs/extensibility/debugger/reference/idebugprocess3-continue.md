---
title: IDebugProcess3::Continue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::Continue
helpviewer_keywords:
- IDebugProcess3::Continue
ms.assetid: 57506242-5763-4c08-adb9-8a78ce02cebb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fefbbbced72a53566ffb726c9ea900e037ee4639
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719337"
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
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
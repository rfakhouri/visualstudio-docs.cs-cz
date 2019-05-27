---
title: IDebugProgram3::ExecuteOnThread | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProgram3::ExecuteOnThread
ms.assetid: 2f5211e3-7a3f-47bf-9595-dfc8b4895d0d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1edd974c934aab5fe3a5c3679190af5ce6039120
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212558"
---
# <a name="idebugprogram3executeonthread"></a>IDebugProgram3::ExecuteOnThread
Spustí ladicí program. Vlákno se vrátí do poskytnout informace o ladicího programu, ve které vlákno je uživatel zobrazení při provádění programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT ExecuteOnThread(
   [in] IDebugThread2* pThread)
```

```csharp
int ExecuteOnThread(
   IDebugThread2 pThread
);
```

## <a name="parameters"></a>Parametry
`pThread`\
[in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objektu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Existují tři způsoby, že ladicí program může pokračovat v provádění po zastavení:

- Spusťte: Zrušit všechny předchozí krok a spusťte až k další zarážce a tak dále.

- Krok: Zrušit všechny původní kroku a spustit, dokud se nedokončí nový krok.

- Pokračujte: Spusťte znovu a ponechání aktivní žádné staré kroku.

  Vlákno předán `ExecuteOnThread` je užitečné, když se budete rozhodovat, ve kterém kroku zrušit. Pokud si nejste jisti vlákno, spusťte zruší všechny kroky. Se znalostí vlákna stačí zrušit kroku na aktivní vlákno.

## <a name="see-also"></a>Viz také:
- [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md)
- [IDebugProgram3](../../../extensibility/debugger/reference/idebugprogram3.md)
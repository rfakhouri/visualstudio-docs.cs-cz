---
title: IDebugProcess2::EnumThreads | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::EnumThreads
helpviewer_keywords:
- IDebugProcess2::EnumThreads
ms.assetid: 05677385-7a7f-4545-8438-af00dde85db0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 664f4264fd12106fef0650a31a888470e09a3154
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353171"
---
# <a name="idebugprocess2enumthreads"></a>IDebugProcess2::EnumThreads
Načte seznam všech vláken spuštěných v rámci procesu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumThreads(
   IEnumDebugThreads2** ppEnum
);
```

```csharp
int EnumThreads(
   out IEnumDebugThreads2 ppEnum
);
```

## <a name="parameters"></a>Parametry
`ppEnum`\
[out] Vrátí [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md) objekt, který obsahuje seznam všech vláken ve všech aplikacích v procesu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda vytvoří výčet vlákna spuštěná v každém programu a kombinuje je do procesu zobrazení vlákna. Jedno vlákno může běžet ve více programech; Tato metoda vytvoří výčet bylo vlákno pouze jednou.

 Tato metoda představuje seznam vláken procesu bez duplicitní položky. V opačném případě se vytvořit výčet vlákna spuštěná v konkrétní aplikaci, použijte [enumthreads –](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) metody.

## <a name="see-also"></a>Viz také:
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)
---
title: IDebugPortEx2::CanTerminateProcess | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEx2::CanTerminateProcess
helpviewer_keywords:
- IDebugPortEx2::CanTerminateProcess
ms.assetid: 111f65d8-5a1a-42b3-9de3-dd9bb03a33fd
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: db1a4fedac88208d54d146a6c5b74b847db21866
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311126"
---
# <a name="idebugportex2canterminateprocess"></a>IDebugPortEx2::CanTerminateProcess
Určuje, zda lze ukončit proces.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CanTerminateProcess( 
   IDebugProcess2* pPortProcess
);
```

```csharp
HRESULT CanTerminateProcess( 
   IDebugProcess2 pPortProcess
);
```

## <a name="parameters"></a>Parametry
`pPortProcess`\
[in] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) objekt reprezentující proces ukončen.

## <a name="return-value"></a>Návratová hodnota
 Vrátí `S_OK` Pokud lze ukončit proces; v opačném případě vrátí `S_FALSE`.

## <a name="see-also"></a>Viz také:
- [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
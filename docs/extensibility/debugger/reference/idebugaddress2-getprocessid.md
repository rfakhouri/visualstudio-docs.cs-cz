---
title: IDebugAddress2::GetProcessID | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress2::GetProcessID
helpviewer_keywords:
- IDebugAddress2::GetProcessID method
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f363ba75d21b147eee6ad39276b949c703e932ee
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324467"
---
# <a name="idebugaddress2getprocessid"></a>IDebugAddress2::GetProcessID
Načte ID procesu, který vlastní objekt reprezentovaný tímto objektem [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md) rozhraní.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetProcessID (
   DWORD* pProcID
);
```

```csharp
int GetProcessID (
   out uint pProcID
);
```

## <a name="parameters"></a>Parametry
`pProcID`\
[out] ID procesu.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)
---
title: IDebugPortEx2::GetPortProcessId | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEx2::GetPortProcessId
helpviewer_keywords:
- IDebugPortEx2::GetPortProcessId
ms.assetid: be85be66-47e6-415f-b0ca-24599aa5f13c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fc1cb77d15c8825e0eb11243b40a08ff8287adbd
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311648"
---
# <a name="idebugportex2getportprocessid"></a>IDebugPortEx2::GetPortProcessId
Získá ID procesu portu samotný.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetPortProcessId ( 
   DWORD* pdwProcessId
);
```

```csharp
int GetPortProcessId ( 
   out uint pdwProcessId
);
```

## <a name="parameters"></a>Parametry
`pdwProcessId`\
[out] Vrátí ID procesu fyzického portu samotný.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 V modulu runtime Win32 například tato metoda obvykle volá funkci Win32 `GetCurrentProcessId` získat ID procesu fyzické.

## <a name="see-also"></a>Viz také:
- [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)
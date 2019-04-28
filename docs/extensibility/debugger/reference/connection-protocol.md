---
title: CONNECTION_PROTOCOL | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CONNECTION_PROTOCOL
helpviewer_keywords:
- CONNECTION_PROTOCOL enumeration
ms.assetid: 99df5865-8b36-486d-9f4c-d10ae2bc688a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2a7d8d056fb816a428d78a8e13455cf6ccdd8a90
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62878266"
---
# <a name="connectionprotocol"></a>CONNECTION_PROTOCOL
Určuje protokol, který používá ke komunikaci mezi serverem pro ladění a ladit balíček (DE).

## <a name="syntax"></a>Syntaxe

```cpp
typedef enum tagCONNECTION_PROTOCOL {
    CONNECTION_NONE    = 0,
    CONNECTION_UNKNOWN = 1,
    CONNECTION_LOCAL   = 2,
    CONNECTION_PIPE    = 3,
    CONNECTION_TCPIP   = 4,
    CONNECTION_HTTP    = 5,
    CONNECTION_OTHER   = 6
} CONNECTION_PROTOCOL;
```

```csharp
public enum CONNECTION_PROTOCOL {
    CONNECTION_NONE    = 0,
    CONNECTION_UNKNOWN = 1,
    CONNECTION_LOCAL   = 2,
    CONNECTION_PIPE    = 3,
    CONNECTION_TCPIP   = 4,
    CONNECTION_HTTP    = 5,
    CONNECTION_OTHER   = 6
};
```

#### <a name="parameters"></a>Parametry
CONNECTION_NONE bez připojení k serveru.

CONNECTION_UNKNOWN A připojení, ale je neznámého typu.

CONNECTION_LOCAL připojení je na místním serveru.

CONNECTION_PIPE připojení je přes pojmenovaný kanál.

CONNECTION_TCPIP připojení používá protokol TCP/IP.

CONNECTION_HTTP připojení používá protokol HTTP (prostřednictvím webového serveru).

CONNECTION_OTHER stal jiný typ připojení (Tato hodnota není aktuálně používá.).

## <a name="remarks"></a>Poznámky
Tyto hodnoty jsou vráceny z [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)

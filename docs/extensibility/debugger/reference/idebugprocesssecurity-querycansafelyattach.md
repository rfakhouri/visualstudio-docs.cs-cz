---
title: IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1e718efddc90c45ced7e497a9c66c9ab3889c090
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311428"
---
# <a name="idebugprocesssecurityquerycansafelyattach"></a>IDebugProcessSecurity::QueryCanSafelyAttach
Tato metoda umožňuje dodavatele portu zobrazila upozornění předtím, než uživatel připojí k unsafe procesu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT QueryCanSafelyAttach();
```

```csharp
int QueryCanSafelyAttach();
```

## <a name="return-value"></a>Návratová hodnota
 Vrácené hodnoty jsou následující:

- `S_OK`: Připojení k procesu je bezpečné a zobrazí se dialogové okno bez upozornění.

- `S_FALSE`: Připojení může být problém se zabezpečením a se zobrazí dialogové okno s upozorněním.

- `FAILURE`: Připojení k procesu se nezdaří.

## <a name="see-also"></a>Viz také:
- [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)
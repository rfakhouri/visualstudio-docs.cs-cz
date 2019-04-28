---
title: IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 891a0c200b02f8768ef68d1d87649bfd35cf59d2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62917535"
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

## <a name="see-also"></a>Viz také
- [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)
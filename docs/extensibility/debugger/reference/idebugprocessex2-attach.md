---
title: IDebugProcessEx2::Attach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcessEx2::Attach
helpviewer_keywords:
- IDebugProcessEx2::Attach method
ms.assetid: f3334ed7-39bf-4d02-a338-36f567b9b287
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5932535810f28e6f5da96ab69457f7364563d622
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66325333"
---
# <a name="idebugprocessex2attach"></a>IDebugProcessEx2::Attach
Tato metoda informuje proces relace je nyní ladění procesu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Attach( 
   IDebugSession2* pSession
);
```

```csharp
int Attach(
   IDebugSession2 pSession
);
```

## <a name="parameters"></a>Parametry
`pSession`\
[in] Hodnota, která jednoznačně identifikuje relace připojení k tomuto procesu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Předané rozhraní `pSession` je považován za pouze do souboru cookie, hodnotu, která jednoznačně identifikuje správce ladění relace připojení k tomuto procesu; žádný z metod na zadané rozhraní není funkční.

## <a name="see-also"></a>Viz také:
- [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)
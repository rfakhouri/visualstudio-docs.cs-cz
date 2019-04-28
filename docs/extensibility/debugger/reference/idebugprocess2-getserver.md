---
title: IDebugProcess2::GetServer | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetServer
helpviewer_keywords:
- IDebugProcess2::GetServer
ms.assetid: 8f73c530-cceb-4f1f-8c63-1cc0ccd4a310
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 33f9b513bcf336cac68af7d915880af0652b0954
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62917762"
---
# <a name="idebugprocess2getserver"></a>IDebugProcess2::GetServer
Získá serveru, na kterém je spuštěn tento proces.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetServer( 
   IDebugCoreServer2** ppServer
);
```

```csharp
int GetServer( 
   out IDebugCoreServer2 ppServer
);
```

#### <a name="parameters"></a>Parametry
 `ppServer`

 [out] Vrátí [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) objekt, který představuje server, na kterém je spuštěný tento proces.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Více než jeden server může běžet na jednom počítači.

## <a name="see-also"></a>Viz také
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)
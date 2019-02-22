---
title: IDebugEngine3::SetEngineGuid | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine3::SetEngineGuid
helpviewer_keywords:
- IDebugEngine3::SetEngineGuid
ms.assetid: 8bdfa05d-feb7-4d98-abac-77825a04c50f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 14c1ad0e659df29c462d145e8c98166079857275
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56702210"
---
# <a name="idebugengine3setengineguid"></a>IDebugEngine3::SetEngineGuid
Tato metoda nastaví stroje ladění (DE) `GUID`.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetEngineGuid(
   GUID* guidEngine
);
```

```csharp
int SetEngineGuid(
   ref Guid guidEngine
);
```

#### <a name="parameters"></a>Parametry
 `guidEngine`

 [in] `GUID` stroje.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)
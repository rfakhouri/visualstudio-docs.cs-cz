---
title: IDebugObject::GetSize | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::GetSize
helpviewer_keywords:
- IDebugObject::GetSize method
ms.assetid: 89af423b-36eb-479d-b2de-2693455eca15
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a44f7c20784ca7f253db1d44c4079603f363d616
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719727"
---
# <a name="idebugobjectgetsize"></a>IDebugObject::GetSize
Získá velikost objektu v bajtech.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetSize( 
   UINT* pnSize
);
```

```csharp
int GetSize(
   out uint pnSize
);
```

#### <a name="parameters"></a>Parametry
 `pnSize`

 [out] Vrátí velikost v bajtech.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Použití [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md) metody k načtení hodnoty jako sekvenci bajtů.

## <a name="see-also"></a>Viz také
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)
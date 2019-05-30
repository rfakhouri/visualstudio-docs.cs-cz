---
title: IDebugArrayField::GetElementType | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayField::GetElementType
helpviewer_keywords:
- IDebugArrayField::GetElementType method
ms.assetid: c46bf625-0a48-4cbb-8f1f-286356f2c065
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 13dabbf61999e8558fe08ecb65169dd43302d98f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66320961"
---
# <a name="idebugarrayfieldgetelementtype"></a>IDebugArrayField::GetElementType
Získá typ prvku v poli.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetElementType( 
   IDebugField** ppType
);
```

```csharp
int GetElementType(
   out IDebugField ppType
);
```

## <a name="parameters"></a>Parametry
`ppType`\
[out] Vrátí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt, který popisuje typ prvku.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md) objektu předpokládá, že všechny prvky pole jsou stejného typu.

## <a name="see-also"></a>Viz také:
- [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
---
title: IDebugArrayObject::GetElements | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetElements
helpviewer_keywords:
- IDebugArrayObject::GetElements method
ms.assetid: f6a6262f-5183-46ce-8a45-33ef46088b98
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 915724fa5790c6b8c9fde2706b1222db239cb4ab
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351799"
---
# <a name="idebugarrayobjectgetelements"></a>IDebugArrayObject::GetElements
Získá enumerátor všech prvků pole.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetElements( 
   IEnumDebugObjects** ppEnum
);
```

```csharp
int GetElements(
   out IEnumDebugObjects ppEnum
);
```

## <a name="parameters"></a>Parametry
`ppEnum`\
[out] Vrátí [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md) objekt, který umožňuje vytváření výčtu přes všechny prvky.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Jako alternativu použijte [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) a [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) metody k iteraci v rámci prvků.

## <a name="see-also"></a>Viz také:
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
---
title: IDebugProperty2::GetParent | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetParent
helpviewer_keywords:
- IDebugProperty2::GetParent
ms.assetid: 58780469-fe25-4d84-9187-67940ca0767f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1cd550cf602ca1333477a699a32e501961c74821
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66342986"
---
# <a name="idebugproperty2getparent"></a>IDebugProperty2::GetParent
Získá vlastnost nadřazené vlastnosti.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetParent ( 
   IDebugProperty2** ppParent
);
```

```csharp
int GetParent ( 
   out IDebugProperty2 ppParent
);
```

## <a name="parameters"></a>Parametry
`ppParent`\
[out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt, který reprezentuje nadřazenou vlastnost.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `S_GETPARENT_NO_PARENT` Pokud není žádný nadřazený objekt.

## <a name="see-also"></a>Viz také:
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
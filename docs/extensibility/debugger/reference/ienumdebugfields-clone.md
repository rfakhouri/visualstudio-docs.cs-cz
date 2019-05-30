---
title: IEnumDebugFields::Clone | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFields::Clone
helpviewer_keywords:
- IEnumDebugFields::Clone method
ms.assetid: 7ec265a8-696f-45ce-a2a2-0a83e96fee1b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2d614a1d98a1374ed0b04aef5b23ebf91c21610c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350446"
---
# <a name="ienumdebugfieldsclone"></a>IEnumDebugFields::Clone
Tato metoda vrátí kopii objektu do aktuálního výčtu jako samostatný objekt.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Clone(
   IEnumDebugFields** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>Parametry
`ppEnum`\
[out] Vrátí kopii objektu tento výčet jako samostatný objekt.

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Kopírování výčet má stejného stavu jako původní v době, kdy tato metoda je volána. Ale tuto kopii a původní stavy jsou oddělené a je možné změnit individuálně.

## <a name="see-also"></a>Viz také
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
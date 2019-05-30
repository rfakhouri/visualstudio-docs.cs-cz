---
title: IDebugClassField::EnumConstructors | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumConstructors
helpviewer_keywords:
- IDebugClassField::EnumConstructors method
ms.assetid: 66a250b2-75a0-45aa-8d58-40f91cc4bf7b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 94a73b5f46e3e6319fef0ac2134966c4a4944279
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66349641"
---
# <a name="idebugclassfieldenumconstructors"></a>IDebugClassField::EnumConstructors
Vytvoří čítač pro konstruktory pro tuto třídu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumConstructors( 
   CONSTRUCTOR_ENUM   cMatch,
   IEnumDebugFields** ppEnum
);
```

```csharp
int EnumConstructors(
   CONSTRUCTOR_ENUM     cMatch,
   out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>Parametry
`cMatch`\
[in] Hodnota z [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md) výčet, který určuje typ pro výčet konstruktory.

`ppEnum`\
[out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam konstruktory. Vrátí hodnotu null, pokud neexistují žádné konstruktory.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádné konstruktory. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Každý prvek výčtu je [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) objekt popisující metodu konstruktoru.

 Seznam konstruktory obvykle neobsahuje výchozí konstruktory poskytnutých kompilátoru.

## <a name="see-also"></a>Viz také:
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)
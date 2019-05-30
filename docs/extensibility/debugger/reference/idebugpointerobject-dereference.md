---
title: IDebugPointerObject::Dereference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::Dereference
helpviewer_keywords:
- IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 381c6f392cccb398497204cc5772c5f9a00fd5b0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66331659"
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
Získá odkazovaný objekt.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT DeReference( 
   DWORD          dwIndex,
   IDebugObject** ppObject
);
```

```csharp
int Dereference(
   uint             dwIndex,
   out IDebugObject ppObject
);
```

## <a name="parameters"></a>Parametry
`dwIndex`\
[in] Ukazuje jednoduchý bajtovým posunem od začátku objektu.

`ppObject`\
[out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt reprezentující objekt odkazovala na plus odsazení, pokud existuje.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby. Pokud tento objekt neodkazuje na jiný objekt, vrátí E_FAIL.

## <a name="remarks"></a>Poznámky
 Odkazovaný objekt může být jednoduchého typu nebo typu složitější například třídy nebo struktury.

## <a name="see-also"></a>Viz také:
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)
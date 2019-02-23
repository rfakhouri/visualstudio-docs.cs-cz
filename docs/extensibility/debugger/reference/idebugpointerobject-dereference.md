---
title: IDebugPointerObject::Dereference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::Dereference
helpviewer_keywords:
- IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f01e863d03f6179ef4c15f50521cc72ba21f5740
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706584"
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

#### <a name="parameters"></a>Parametry
 `dwIndex`

 [in] Ukazuje jednoduchý bajtovým posunem od začátku objektu.

 `ppObject`

 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt reprezentující objekt odkazovala na plus odsazení, pokud existuje.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby. Pokud tento objekt neodkazuje na jiný objekt, vrátí E_FAIL.

## <a name="remarks"></a>Poznámky
 Odkazovaný objekt může být jednoduchého typu nebo typu složitější například třídy nebo struktury.

## <a name="see-also"></a>Viz také
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)
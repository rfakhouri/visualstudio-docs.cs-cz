---
title: IDebugObject2::CreateAlias | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::CreateAlias
helpviewer_keywords:
- IDebugObject2::CreateAlias method
ms.assetid: 54a05920-5d13-4f67-962b-d1a7f013dff9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 226d584a2773a342b8247ff337e686be2da6bf9b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62843032"
---
# <a name="idebugobject2createalias"></a>IDebugObject2::CreateAlias
Vytvoří jedinečné ID nebo alias pro tento objekt nebo vrátí existující alias.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CreateAlias(
   IDebugAlias** ppAlias
);
```

```csharp
int CreateAlias(
   out IDebugAlias ppAlias
);
```

#### <a name="parameters"></a>Parametry
 `ppAlias`

 [out] Nový (nebo existující) alias.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Alias je popisek, který představuje určitý objekt, pokud je objekt v paměti.

## <a name="see-also"></a>Viz také
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)
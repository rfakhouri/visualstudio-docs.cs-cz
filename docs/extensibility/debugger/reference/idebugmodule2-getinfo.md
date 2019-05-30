---
title: IDebugModule2::GetInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugModule2::GetInfo method
ms.assetid: de337e66-294f-4ac9-b21e-71fac7418e36
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1fe5060f66c56a033fb0bdcc8ae7dee368d2824e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66323973"
---
# <a name="idebugmodule2getinfo"></a>IDebugModule2::GetInfo
Získá informace o tomto modulu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetInfo( 
   MODULE_INFO_FIELDS dwFields,
   MODULE_INFO*       pInfo
);
```

```cpp
int GetInfo( 
   enum_MODULE_INFO_FIELDS dwFields,
   MODULE_INFO[]           pInfo
);
```

## <a name="parameters"></a>Parametry
`dwFields`\
[in] Kombinace příznaků z [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) výčtu, která pole zadáte `pInfo` mají doplnit.

`pInfo`\
[out v] A [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) struktura, která se vyplní popis modulu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) struktura obsahuje název modulu, který se zobrazí **moduly** okna.

## <a name="see-also"></a>Viz také:
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)
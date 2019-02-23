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
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a0a5ad3d7651e89c2ef864a184155e8b0a430d79
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694800"
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

#### <a name="parameters"></a>Parametry
 `dwFields`

 [in] Kombinace příznaků z [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) výčtu, která pole zadáte `pInfo` mají doplnit.

 `pInfo`

 [out v] A [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) struktura, která se vyplní popis modulu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) struktura obsahuje název modulu, který se zobrazí **moduly** okna.

## <a name="see-also"></a>Viz také
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)
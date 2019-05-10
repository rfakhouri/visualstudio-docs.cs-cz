---
title: IDebugReference2::GetDerivedMostReference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::GetDerivedMostReference
helpviewer_keywords:
- IDebugReference2::GetDerivedMostReference
ms.assetid: 07253b74-7d39-48e0-8e85-ac8dfd919f6e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ba770dec92054f68c3cb95433d2a2c83bdb37bce
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457501"
---
# <a name="idebugreference2getderivedmostreference"></a>IDebugReference2::GetDerivedMostReference
Získá odkaz na nejvíce odvozené odkaz. Vyhrazeno pro budoucí použití.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDerivedMostReference( 
   IDebugReference2** ppDerivedMost
);
```

```csharp
int GetDerivedMostReference( 
   out IDebugReference2 ppDerivedMost
);
```

## <a name="parameters"></a>Parametry
 `ppDerivedMost`\

 [out] Vrátí [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt, který reprezentuje vlastnost nejvíce odvozené.

## <a name="return-value"></a>Návratová hodnota
 Vždy vrátí `E_NOTIMPL`.

## <a name="remarks"></a>Poznámky
 Například, pokud je tato vlastnost popisuje objekt, který implementuje `ClassRoot` , ale která je ve skutečnosti instance `ClassDerived` , která je odvozena od `ClassRoot`, pak tato metoda vrátí [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objektu představuje odkaz na `ClassDerived` objektu.

## <a name="see-also"></a>Viz také:
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
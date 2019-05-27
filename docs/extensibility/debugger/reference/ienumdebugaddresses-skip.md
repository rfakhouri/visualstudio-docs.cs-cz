---
title: IEnumDebugAddresses::Skip | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugAddresses::Skip
helpviewer_keywords:
- IEnumDebugAddresses::Skip method
ms.assetid: ed9a8e71-30ef-414b-9da5-c9a2a251b84e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e98e10267a23813ec20347ed517df0b36508ada4
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66208557"
---
# <a name="ienumdebugaddressesskip"></a>IEnumDebugAddresses::Skip
Tato metoda přeskočí za zadaný počet prvků.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Skip(
   [in] ULONG celt
);
```

```csharp
int Skip(
   uint celt
);
```

## <a name="parameters"></a>Parametry
`celt`\
[in] Počet prvků, které mají přeskočit.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud `celt` je větší než počet zbývajících prvků; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pokud `celt` Určuje hodnotu větší než počet zbývajících prvků výčtu je nastavena na konci a `S_FALSE` je vrácena.

## <a name="see-also"></a>Viz také:
- [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)
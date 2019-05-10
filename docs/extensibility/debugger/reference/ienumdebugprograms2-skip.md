---
title: IEnumDebugPrograms2::Skip | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPrograms2::Skip
helpviewer_keywords:
- IEnumDebugPrograms2::Skip
ms.assetid: b283858b-b375-4760-bfec-ab37de89958d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2144f0bb4c59236bf4a4fbaff11106a08eb7f7f3
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65226443"
---
# <a name="ienumdebugprograms2skip"></a>IEnumDebugPrograms2::Skip
Přeskočí za zadaný počet prvků.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Skip(
   ULONG celt
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
- [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)
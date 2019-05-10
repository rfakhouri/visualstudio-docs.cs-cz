---
title: IEnumDebugErrorBreakpoints2::GetCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugErrorBreakpoints2::GetCount
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2::GetCount
ms.assetid: 56f7bb70-d55b-471c-8c65-09a9e7f4938e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c76900321746a6d75e16e0c423ddf7dfbc25dca0
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225904"
---
# <a name="ienumdebugerrorbreakpoints2getcount"></a>IEnumDebugErrorBreakpoints2::GetCount
Vrátí počet prvků ve výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetCount(
   ULONG* pcelt
);
```

```csharp
int GetCount(
   out uint pcelt
);
```

## <a name="parameters"></a>Parametry
 `pcelt`\

 [out] Vrátí počet prvků ve výčtu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda není součástí obvyklé výčet rozhraní modelu COM, který určuje pouze `Next`, `Clone`, `Skip`, a `Reset` potřeba je implementovat metody.

## <a name="see-also"></a>Viz také:
- [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)
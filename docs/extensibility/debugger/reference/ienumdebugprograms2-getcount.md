---
title: IEnumDebugPrograms2::GetCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPrograms2::GetCount
helpviewer_keywords:
- IEnumDebugPrograms2::GetCount
ms.assetid: 84832982-fa68-4090-a5b7-b233817876b7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 795404d0cae2dd5cbf4f6f913b3ba71cf3fe34a0
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65223442"
---
# <a name="ienumdebugprograms2getcount"></a>IEnumDebugPrograms2::GetCount
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
- [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)
---
title: IEnumCodePaths2::GetCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumCodePaths2::GetCount
helpviewer_keywords:
- IEnumCodePaths2::GetCount
ms.assetid: 988c5092-fcc5-43a1-a94c-c261edd56ebf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9059a080d9d128517f636b00a7a8b285c5be1dc9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56688495"
---
# <a name="ienumcodepaths2getcount"></a>IEnumCodePaths2::GetCount
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

#### <a name="parameters"></a>Parametry
 `pcelt`

 [out] Vrátí počet prvků ve výčtu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda není součástí obvyklé výčet rozhraní modelu COM, který určuje pouze `Next`, `Clone`, `Skip`, a `Reset` potřeba je implementovat metody.

## <a name="see-also"></a>Viz také
- [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)
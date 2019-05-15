---
title: IDebugArrayObject::GetDimensions | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetDimensions
helpviewer_keywords:
- IDebugArrayObject::GetDimensions method
ms.assetid: 113e0aff-9028-49d6-b104-9fe7be4772d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 60ee75454bf105f12b79d60e032549bcb84ab465
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615235"
---
# <a name="idebugarrayobjectgetdimensions"></a>IDebugArrayObject::GetDimensions
Získá rozměry pole.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDimensions( 
   DWORD dwCount,
   DWORD dwDimensions[]
);
```

```csharp
int GetDimensions(
   [In] uint    dwCount,
   [Out] uint[] dwDimensions
);
```

## <a name="parameters"></a>Parametry
`dwCount`\
[in] Počet dimenzí pro načtení.

`dwDimensions`\
[out v] Pole, které se vyplní velikosti jednotlivých rozměrů. `dwCount` Určuje maximální velikost `dwDimensions` pole.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Vícerozměrné pole může mít různé velikosti pro jednotlivé rozměry. Mějme například trojrozměrného pole `myarray[3][2][6]`, vrátí tato metoda 3, 2 a 6 `dwDimensions` parametrů v tomto pořadí.

## <a name="see-also"></a>Viz také:
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
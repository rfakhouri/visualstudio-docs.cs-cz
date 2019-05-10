---
title: IPropertyProxyEESide::CreateReplacementObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::CreateReplacementObject
helpviewer_keywords:
- IPropertyProxyEESide::CreateReplacementObject
ms.assetid: 0cfe79b8-c3f1-48b0-a225-e39dee2c92fe
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c8a5c9a05525c55d35bb6e0033c5c2abcacbbc97
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458142"
---
# <a name="ipropertyproxyeesidecreatereplacementobject"></a>IPropertyProxyEESide::CreateReplacementObject
Vytvoří kopii datového objektu specifické pro vyhodnocovací filtr výrazů (EE).

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CreateReplacementObject(
   IEEDataStorage*  dataIn,
   IEEDataStorage** dataOut
);
```

```csharp
int CreateReplacementObject(
   IEEDataStorage     dataIn,
   out IEEDataStorage dataOut
);
```

## <a name="parameters"></a>Parametry
 `dataIn`\

 [in] [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objekt obsahující data, které se mají zkopírovat.

 `dataOut`\

 [out] Vrátí nový `IEEDataStorage` objektu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda je uvedena [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objekt představující pole bajtů. Tento objekt příchozích dat se většinou implementují moduly EE. Ale objekt vrácený touto metodou je vždy implementované EE, který umožňuje implementovat EE `IEEDataStorage` rozhraní na libovolné třídy je žádoucí.

 Všimněte si, že data poskytnutých příchozí `IEEDataStorage` objekt musí být stejná data v odchozích dat `IEEDataStorage` objektu.

## <a name="see-also"></a>Viz také:
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
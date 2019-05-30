---
title: IPropertyProxyEESide::InPlaceUpdateObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::InPlaceUpdateObject
helpviewer_keywords:
- IPropertyProxyEESide::InPlaceUpdateObject
ms.assetid: abf89411-1853-4f23-b244-d5e0afa197b1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6ce2826aa0bd75638d6f5ee8086cbcce96517ce7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66329421"
---
# <a name="ipropertyproxyeesideinplaceupdateobject"></a>IPropertyProxyEESide::InPlaceUpdateObject
Aktualizuje data objektu s danou datový objekt a vrátí nový datový objekt reprezentující objektu nová data.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT InPlaceUpdateObject(
   [in] IEEDataStorage*   dataIn,
   [out] IEEDataStorage** dataOut
);
```

```csharp
int InPlaceUpdateObject(
   IEEDataStorage     dataIn,
   out IEEDataStorage dataOut
);
```

## <a name="parameters"></a>Parametry
`dataIn`\
[in] [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objekt, který obsahuje nová data.

`dataOut`\
[out] Vrátí nový `IEEDataStorage` objekt, který obsahuje data nahrazené.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda ve skutečnosti aktualizuje data objektu. Data ve vráceném [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objektu nemusí být stejné jako data v příchozí `IEEDataStorage` objektu, ale vráceného objektu musí odpovídat aktuální hodnota vlastnosti.

 Příchozí datový objekt není většinou implementují moduly EE. Ale objekt vrácený touto metodou je vždy implementované EE, který umožňuje implementovat EE `IEEDataStorage` rozhraní na libovolné třídy je žádoucí.

 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) metoda vytvoří datový objekt na základě příchozích dat objektu, ale nemá vliv na původní data vlastnosti.

## <a name="see-also"></a>Viz také:
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
- [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)
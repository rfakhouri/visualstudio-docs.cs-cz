---
title: IPropertyProxyEESide::InitSourceDataProvider | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::InitSourceDataProvider
helpviewer_keywords:
- IPropertyProxyEESide::InitSourceDataProvider
ms.assetid: 5156f593-5052-4e3a-9d02-081916fb342d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a6791c4a88ae0440dbc6cee12e0f5b5e353e0d69
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66198788"
---
# <a name="ipropertyproxyeesideinitsourcedataprovider"></a>IPropertyProxyEESide::InitSourceDataProvider
Inicializuje zdrojová data pro tento objekt a vrátí objekt, který obsahuje původní data.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT InitSourceDataProvider(
   IEEDataStorage** dataOut
);
```

```csharp
int InitSourceDataProvider(
   out IEEDataStorage dataOut
);
```

## <a name="parameters"></a>Parametry
`dataOut`\
[out] Vrátí [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objektu

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda provádí všechno, co je potřeba inicializovat objekt, abyste ji mohli vrátit [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) rozhraní pro data objektu. To umožňuje objektu data k zobrazení a, pokud je povoleno, změnil(a) vizualizér typů.

## <a name="see-also"></a>Viz také:
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
---
title: IDebugEnumField::GetUnderlyingSymbol | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEnumField::GetUnderlyingSymbol
helpviewer_keywords:
- IDebugEnumField::GetUnderlyingSymbol method
ms.assetid: c3b8a117-6708-4cfd-8ffc-5f007d706bc5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9b6b90f388f93bc7cfc2c246c529217bcdb00fa9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920278"
---
# <a name="idebugenumfieldgetunderlyingsymbol"></a>IDebugEnumField::GetUnderlyingSymbol
Tato metoda vrátí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) , která představuje název výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetUnderlyingSymbol(
   IDebugField** ppField
);
```

```csharp
int GetUnderlyingSymbol(
   out IDebugField ppField
);
```

#### <a name="parameters"></a>Parametry
 `ppField`

 [out] Vrátí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) popisující název tento výčet.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Název výčtu obsahuje také typ výčtu, který je vázán na umístění v paměti pomocí [svázat](../../../extensibility/debugger/reference/idebugbinder-bind.md).

## <a name="see-also"></a>Viz také
- [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md)
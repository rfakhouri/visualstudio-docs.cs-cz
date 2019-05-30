---
title: IEEVisualizerServiceProvider::CreateVisualizerService | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService
helpviewer_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService method
ms.assetid: f366f7c9-358d-46c8-993f-32ff86539833
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 20a8180283e596eeb9dd4ee1391e6e8fe6666829
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66310164"
---
# <a name="ieevisualizerserviceprovidercreatevisualizerservice"></a>IEEVisualizerServiceProvider::CreateVisualizerService
Tato metoda vytvoří vizualizační službou.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CreateVisualizerService(
   IDebugBinder*              binder,
   IDebugSymbolProvider*      pSymProv,
   IDebugAddress*             pAddress,
   IEEVisualizerDataProvider* dataProvider,
   IEEVisualizerService**     ppService
);
```

```csharp
int CreateVisualizerService(
   IDebugBinder binder,
   IDebugSymbolProvider      pSymProv,
   IDebugAddress             pAddress,
   IEEVisualizerDataProvider dataProvider,
   out IEEVisualizerService  ppService
);
```

## <a name="parameters"></a>Parametry
`binder`\
[in] [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) předán objekt [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md).

`pSymProv`\
[in] [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) předán objekt `IDebugParsedExpression::EvaluateSync`.

`pAddress`\
[in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) předán objekt `IDebugParsedExression::EvaluateSync`.

`dataProvider`\
[in] Implementaci objektu [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) rozhraní (zadané ve vyhodnocovací filtr výrazů).

`ppService`\
[out] Vytvořená služba.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 `binder`, `pSymProv`, A `pAddress` parametry byly předány do `IDebugParsedExpression::EvaluateSync` metody. `CreateVisualizerService` je možné volat pouze z `IDebugParsedExpression::EvaluateSync` jako součást podpory vyhodnocovač výrazů pro vizualizérů typů.

## <a name="see-also"></a>Viz také:
- [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
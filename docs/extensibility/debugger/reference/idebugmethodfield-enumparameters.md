---
title: IDebugMethodField::EnumParameters | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4d455d380f66689cd2245070a7ef0bf9290a2455
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324224"
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
Vytvoří čítač pro parametry metody.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumParameters( 
   IEnumDebugFields** ppParams
);
```

```csharp
int EnumParameters(
   out IEnumDebugFields ppParams
);
```

## <a name="parameters"></a>Parametry
`ppParams`\
[out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam parametrů metody; v opačném případě vrátí hodnotu null, pokud neexistují žádné parametry.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádné parametry. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Každý prvek je [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu, který představuje různé typy parametrů. Volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) metoda na každém objektu k určení přesně jaký druh parametr objekt představuje.

 Parametr zahrnuje jeho název proměnné a jeho typu. První parametr metody třídy je obvykle ukazatel "Tento".

 Pokud pouze typy parametrů je potřeba, zavolejte [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) metody.

## <a name="see-also"></a>Viz také:
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)
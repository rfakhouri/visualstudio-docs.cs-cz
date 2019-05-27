---
title: IDebugExpressionContext2::GetName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionContext2::GetName
helpviewer_keywords:
- IDebugExpressionContext2::GetName
ms.assetid: c2b70d22-17af-4986-a7e3-930910367216
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1961ac778dab2d17a87748cae8e1210f6b13422d
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66201062"
---
# <a name="idebugexpressioncontext2getname"></a>IDebugExpressionContext2::GetName
Načte název kontext vyhodnocení.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetName( 
   BSTR* pbstrName
);
```

```csharp
int GetName( 
   out string pbstrName
);
```

## <a name="parameters"></a>Parametry
`pbstrName`\
[out] Vrátí název kontext vyhodnocení.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Název je popis tento kontext vyhodnocení. Je to obvykle něco, může být analyzován metodou vyhodnocovače výrazů, který odkazuje na tento kontext vyhodnocení přesné. Například v jazyce C++ název vypadá takto:

```
"{ function-name, source-file-name, module-file-name }"
```

## <a name="see-also"></a>Viz také:
- [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)
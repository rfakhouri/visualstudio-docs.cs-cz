---
title: IDebugField::Equal | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::Equal
helpviewer_keywords:
- IDebugField::Equal method
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: bfee65537512398cad2f4b86d51ebefac230fb1c
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212230"
---
# <a name="idebugfieldequal"></a>IDebugField::Equal
Tato metoda porovnává tohoto pole se zadaným polem pro rovnost.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Equal( 
   IDebugField* pField
);
```

```csharp
int Equal(
   IDebugField pField
);
```

## <a name="parameters"></a>Parametry
`pField`\
[in] Pole má být porovnán s tohoto objektu.

## <a name="return-value"></a>Návratová hodnota
 Pokud pole jsou stejné, vrátí `S_OK`. Pokud pole liší, vrátí `S_FALSE.` v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
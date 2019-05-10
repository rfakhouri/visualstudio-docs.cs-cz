---
title: IDebugReference2::Compare | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::Compare
helpviewer_keywords:
- IDebugReference2::Compare
ms.assetid: 3361c495-2673-4b7c-82e3-dee74e1fa58d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: df878cc59a47a8d3cc7079f8b919f87d9bb60f43
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457487"
---
# <a name="idebugreference2compare"></a>IDebugReference2::Compare
Porovná jeden odkaz na jiný. Vyhrazeno pro budoucí použití.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Compare ( 
   REFERENCE_COMPARE dwCompare,
   IDebugReference2* pReference
);
```

```csharp
int Compare ( 
   enum_REFERENCE_COMPARE dwCompare,
   IDebugReference2       pReference
);
```

## <a name="parameters"></a>Parametry
 `dwCompare`\

 [in] Hodnota z [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md) výčet, který určuje operaci porovnání, například rovno, menší nebo větší.

 `pReference`\

 [in] [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt představující odkaz k porovnání s.

## <a name="return-value"></a>Návratová hodnota
 Vždy vrátí `E_NOTIMPL`.

## <a name="see-also"></a>Viz také:
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md)
---
title: IEnumDebugReferenceInfo2::Reset | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugReferenceInfo2::Reset
helpviewer_keywords:
- IEnumDebugReferenceInfo2::Reset
ms.assetid: cf8ce649-5ce1-44a6-9d5a-89760021bde4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b405c3183dc59e8b7e124b5c93cb12b819933e96
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65461257"
---
# <a name="ienumdebugreferenceinfo2reset"></a>IEnumDebugReferenceInfo2::Reset
Obnoví výčtu na první prvek.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Reset(
   void
);
```

```csharp
int Reset();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Až tato metoda je volána, další volání [Další](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-next.md) metoda vrátí první prvek výčtu.

## <a name="see-also"></a>Viz také:
- [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)
---
title: IDebugCoreServer2::EnumPortSuppliers | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer2::EnumPortSuppliers
helpviewer_keywords:
- IDebugCoreServer2::EnumPortSuppliers
ms.assetid: ce0c90e4-8e02-4b08-b558-7677fb2c88f7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 22c85e4fbdeac2aadf9cb412c367721a923847c0
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723458"
---
# <a name="idebugcoreserver2enumportsuppliers"></a>IDebugCoreServer2::EnumPortSuppliers
Načte seznam všech dostupných portů dodavatelů.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumPortSuppliers(
   IEnumDebugPortSuppliers2** ppEnum
);
```

```csharp
int EnumPortSuppliers(
   out IEnumDebugPortSuppliers2 ppEnum
);
```

#### <a name="parameters"></a>Parametry
 `ppEnum`

 [out] Vrátí [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md) objekt, který obsahuje seznam všech dodavatelé portů.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)
- [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)
---
title: IEnumDebugCustomAttributes::Clone | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumCustomAttributes::Clone
helpviewer_keywords:
- IEnumDebugCustomAttributes::Clone
ms.assetid: e6825000-e195-42b4-b296-bfe1e533d79b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2b1b915b1fa992ad3534117333a85e6bd1875315
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62867389"
---
# <a name="ienumdebugcustomattributesclone"></a>IEnumDebugCustomAttributes::Clone
Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Clone ( 
   IEnumCustomAttributes** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugCustomAttributes ppEnum
);
```

#### <a name="parameters"></a>Parametry
 ppEnum

 [out] Vrátí kopii objektu tento výčet jako samostatný objekt.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Kopírování výčet má stejného stavu jako původní v době, kdy tato metoda je volána. Ale tuto kopii a původní stavy jsou oddělené a je možné změnit individuálně.

## <a name="see-also"></a>Viz také
- [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)
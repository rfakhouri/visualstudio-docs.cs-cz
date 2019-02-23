---
title: IDebugGenericFieldInstance::TypeArgumentCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- TypeArgumentCount
- IDebugGenericFieldInstance::TypeArgumentCount
ms.assetid: e662c5ea-a5c1-478e-a268-5980dadffcd1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b5a6b55d51cd2db25da1b51af84172d64c682245
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689938"
---
# <a name="idebuggenericfieldinstancetypeargumentcount"></a>IDebugGenericFieldInstance::TypeArgumentCount
Vrátí číslo typu parametru argumenty pro tuto instanci.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT TypeArgumentCount(
   ULONG32* pcArgs
);
```

```csharp
int TypeArgumentCount(
   ref uint pcArgs
);
```

#### <a name="parameters"></a>Parametry
 `pcArgs`

 [out v] Počet argumentů pro parametr typu pro tuto instanci.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Například pokud seznam\<int >, tato metoda vrátí hodnotu 1 a pokud je seznam\<int, float2 > Tato metoda vrátí hodnotu 2. Tato metoda vrátí hodnotu 0, pokud nejsou žádné argumenty typu.

## <a name="see-also"></a>Viz také
- [IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)
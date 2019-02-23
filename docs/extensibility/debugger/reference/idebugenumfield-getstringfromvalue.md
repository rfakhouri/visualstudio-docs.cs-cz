---
title: IDebugEnumField::GetStringFromValue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEnumField::GetStringFromValue
helpviewer_keywords:
- IDebugEnumField::GetStringFromValue method
ms.assetid: 5f95fd0c-fdce-497f-9f54-2ad8749494e9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 98d7e976e0cd37ad1397666471c89da3d47d45d3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56710367"
---
# <a name="idebugenumfieldgetstringfromvalue"></a>IDebugEnumField::GetStringFromValue
Tato metoda získává název zadaný hodnotou konstanty výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetStringFromValue(
   ULONGLONG value,
   BSTR*     pbstrValue
);
```

```csharp
int GetStringFromValue(
   ulong      value,
   out string pbstrValue
);
```

#### <a name="parameters"></a>Parametry
 `value`

 [in] Hodnota, pro které chcete získat název výčtu konstant.

 `pbstrValue`

 [out] Vrátí název konstanty výčtu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` Pokud hodnota nemá žádný přidružený název nebo vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pokud existuje více než jeden název spojený se stejnou hodnotou, bude vrácena křestní jméno definované ve výčtu.

## <a name="see-also"></a>Viz také
- [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
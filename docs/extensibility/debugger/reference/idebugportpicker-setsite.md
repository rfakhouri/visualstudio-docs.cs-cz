---
title: IDebugPortPicker::SetSite | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortPicker::SetSite
ms.assetid: 7319e187-adfe-4b3f-aec9-521356fb5a8a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a0964c94334ca0815b4410f6858dca5502b2f8a1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62918153"
---
# <a name="idebugportpickersetsite"></a>IDebugPortPicker::SetSite
Nastaví poskytovatele služeb.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetSite(
   IServiceProvider * pSP
);
```

```csharp
public int SetSite(
   IServiceProvider pSP
);
```

#### <a name="parameters"></a>Parametry
 `pSP`

 [in] Odkaz na rozhraní poskytovatele služeb.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda bude volána před všechny ostatní metody jsou volány.

## <a name="see-also"></a>Viz také
- [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)
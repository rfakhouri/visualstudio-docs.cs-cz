---
title: IDebugSettingsCallback2::GetEELocalObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetEELocalObject
ms.assetid: e69a3469-a049-420c-b918-c48a1e7b9baf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7e6bf186d8b4bf660cc4a22e962754e859378674
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68202471"
---
# <a name="idebugsettingscallback2geteelocalobject"></a>IDebugSettingsCallback2::GetEELocalObject
Načte objekt místní Chyba při vyhodnocování výrazu daný název metriky.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEELocalObject(
   REFGUID     guidLang,
   REFGUID     guidVendor,
   LPCWSTR     pszMetric,
   IUnknown ** ppUnk
);
```

```csharp
private int GetEELocalObject(
   ref Guid          guidLang,
   ref Guid          guidVendor,
   string            pszMetric,
   out System.Object ppUnk
);
```

#### <a name="parameters"></a>Parametry
 `guidLang`

 [in] Jedinečný identifikátor programovací jazyk.

 `guidVendor`

 [in] Jedinečný identifikátor na dodavatele.

 `pszMetric`

 [in] Název metriky.

 `ppUnk`

 [out] Vrátí výraz Chyba při vyhodnocování místní objekt.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)
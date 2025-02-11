---
title: IDebugSettingsCallback2::GetEEMetricGuid | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetEEMetricGuid
ms.assetid: 3d70c19a-595d-44f1-a7b3-a0cf8f15e371
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b1cf70c424856b93eb4d082a167bc671b885a346
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68155194"
---
# <a name="idebugsettingscallback2geteemetricguid"></a>IDebugSettingsCallback2::GetEEMetricGuid
Získá jedinečný identifikátor pro metriku Chyba při vyhodnocování výrazu jeho název.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEEMetricGuid(
   REFGUID guidLang,
   REFGUID guidVendor,
   LPCWSTR pszMetric,
   GUID*   pguidValue
);
```

```csharp
HRESULT GetEEMetricGuid(
   ref Guid guidLang,
   ref Guid guidVendor,
   string   pszMetric,
   out Guid pguidValue
);
```

#### <a name="parameters"></a>Parametry
 `guidLang`

 [in] Jedinečný identifikátor programovací jazyk.

 `guidVendor`

 [in] Jedinečný identifikátor na dodavatele.

 `pszMetric`

 [in] Název metriky.

 `pguidValue`

 [out] Vrací jedinečný identifikátor metriky.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)
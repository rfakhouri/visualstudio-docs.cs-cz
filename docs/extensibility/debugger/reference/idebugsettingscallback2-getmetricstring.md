---
title: IDebugSettingsCallback2::GetMetricString | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetMetricString
- GetMetricString
ms.assetid: ecc875a2-8ac6-444c-a839-5191a780fd6b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d3fdfd604f28f6657b27ef0e81ca4ce5855d97df
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457295"
---
# <a name="idebugsettingscallback2getmetricstring"></a>IDebugSettingsCallback2::GetMetricString
Načte řetězec hodnoty metriky jeho název.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetMetricString(
    LPCWSTR pszType,
    REFGUID guidSection,
    LPCWSTR pszMetric,
    BSTR*   pbstrValue
);
```

```csharp
private int GetMetricString(
    string     pszType,
    ref Guid   guidSection,
    string     pszMetric,
    out string pbstrValue
);
```

## <a name="parameters"></a>Parametry
 `pszType`\

 [in] Typ metriky.

 `guidSection`\

 [in] Jedinečný identifikátor oddílu.

 `pszMetric`\

 [in] Název metriky.

 `pbstrValue`\

 [out] Vrátí řetězec hodnoty metriky.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)
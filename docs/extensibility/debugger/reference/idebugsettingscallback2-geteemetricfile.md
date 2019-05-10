---
title: IDebugSettingsCallback2::GetEEMetricFile | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetEEMetricFile
ms.assetid: 3a0bf9e5-bbd2-4d15-840d-8244732787fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e800d8d57d34c0ed99cb3cfa9a3f6a7b871a034d
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458609"
---
# <a name="idebugsettingscallback2geteemetricfile"></a>IDebugSettingsCallback2::GetEEMetricFile
Načte soubor metriky Chyba při vyhodnocování výrazu danou název nebo metriku.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEEMetricFile(
   REFGUID guidLang,
   REFGUID guidVendor,
   LPCWSTR pszMetric,
   BSTR*   pbstrValue
);
```

```csharp
private int GetEEMetricFile(
   ref Guid   guidLang,
   ref Guid   guidVendor,
   string     pszMetric,
   out string pbstrValue
);
```

## <a name="parameters"></a>Parametry
 `guidLang`\

 [in] Jedinečný identifikátor programovací jazyk.

 `guidVendor`\

 [in] Jedinečný identifikátor na dodavatele.

 `pszMetric`\

 [in] Název metriky.

 `pbstrValue`\

 [out] Vrátí obsah souboru metriky jako řetězec.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)
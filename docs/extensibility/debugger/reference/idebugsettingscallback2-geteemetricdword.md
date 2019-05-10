---
title: IDebugSettingsCallback2::GetEEMetricDword | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetEEMetricDword
ms.assetid: c5f8f417-0ef0-4fd0-a779-b0a8ead4effe
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b3c8349b8a7f7b823d4596f167889a227b166b7a
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457372"
---
# <a name="idebugsettingscallback2geteemetricdword"></a>IDebugSettingsCallback2::GetEEMetricDword
Načte hodnotu, která odpovídá zadané metriky vyhodnocovací filtr výrazů.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEEMetricDword(
   REFGUID guidLang,
   REFGUID guidVendor,
   LPCWSTR pszMetric,
   DWORD*  pdwValue
);
```

```csharp
private int GetEEMetricDword(
   ref Guid guidLang,
   ref Guid guidVendor,
   string   pszMetric,
   out uint pdwValue
);
```

## <a name="parameters"></a>Parametry
 `guidLang`\

 [in] Jedinečný identifikátor programovací jazyk.

 `guidVendor`\

 [in] Jedinečný identifikátor na dodavatele.

 `pszMetric`\

 [in] Název metriky.

 `pdwValue`\

 [out] Vrátí hodnotu, která odpovídá na metriky řetězec.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)
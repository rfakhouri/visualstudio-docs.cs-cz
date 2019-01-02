---
title: IDebugSettingsCallback2::GetEEMetricString | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugSettingsCallback2::GetEEMetricString
ms.assetid: 85e3c093-6a91-4101-ab32-d8ac6eed4918
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a5ab0d970bb7ecc499731a452d414c8868aae530
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53848218"
---
# <a name="idebugsettingscallback2geteemetricstring"></a>IDebugSettingsCallback2::GetEEMetricString
Načte hodnotu řetězce metriku Chyba při vyhodnocování výrazu jeho název.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetEEMetricString(  
   REFGUID guidLang,  
   REFGUID guidVendor,  
   LPCWSTR pszMetric,  
   BSTR*   pbstrValue  
);  
```  
  
```csharp  
private int GetEEMetricString(  
   ref Guid   guidLang,  
   ref Guid   guidVendor,  
   string     pszMetric,  
   out string pbstrValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidLang`  
 [in] Jedinečný identifikátor programovací jazyk.  
  
 `guidVendor`  
 [in] Jedinečný identifikátor na dodavatele.  
  
 `pszMetric`  
 [in] Název metriky.  
  
 `pbstrValue`  
 [out] Vrátí řetězec hodnota metriky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)
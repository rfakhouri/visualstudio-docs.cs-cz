---
title: IDebugSettingsCallback2::GetMetricDword | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugSettingsCallback2::GetMetricDword
ms.assetid: 831a5a1a-c4af-4520-9fdf-3a731aeff85c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9f270678512e21fea9123acbef1310108784bb1b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugsettingscallback2getmetricdword"></a>IDebugSettingsCallback2::GetMetricDword
Načte hodnotu metriky její název.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMetricDword(  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   DWORD*  pdwValue  
);  
```  
  
```csharp  
private int GetMetricDword(  
   string   pszType,  
   ref Guid guidSection,  
   string   pszMetric,  
   out uint pdwValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszType`  
 [v] Typ metriky.  
  
 `guidSection`  
 [v] Jedinečný identifikátor oddílu.  
  
 `pszMetric`  
 [v] Název metriky.  
  
 `pdwValue`  
 [out] Vrátí hodnotu metriky.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)
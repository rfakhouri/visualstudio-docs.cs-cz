---
title: IDebugEngine2::SetMetric | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngine2:::SetMetric
helpviewer_keywords:
- IDebugEngine2:::SetMetric
ms.assetid: dcda4972-c32e-4693-a0e1-25d5c58b9782
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 49208b4ef01d3f1a8cc22abe6d9a926089febed1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengine2setmetric"></a>IDebugEngine2::SetMetric
Tato metoda nastaví hodnotu registru označuje jako metriky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetMetric(  
   LPCOLESTR pszMetric,  
   VARIANT   varValue  
);  
```  
  
```csharp  
int SetMetric(  
   string pszMetric,  
   object varValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszMetric`  
 [v] Název metriky.  
  
 `varValue`  
 [v] Určuje hodnotu, metriky.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Metrika je hodnota registru použít změnit chování modul ladění nebo inzerovat podporované funkce. Tato metoda může předávat volání příslušné formu [SDK pomocníci pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) funkce, `SetMetric`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
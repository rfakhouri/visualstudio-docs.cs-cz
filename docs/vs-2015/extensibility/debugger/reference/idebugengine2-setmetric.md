---
title: IDebugEngine2::SetMetric | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine2:::SetMetric
helpviewer_keywords:
- IDebugEngine2:::SetMetric
ms.assetid: dcda4972-c32e-4693-a0e1-25d5c58b9782
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3371925894a32bfe954979d1554d96d3d5bbb140
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68182238"
---
# <a name="idebugengine2setmetric"></a>IDebugEngine2::SetMetric
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda nastaví hodnotu registru označované jako metriku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT SetMetric(  
   LPCOLESTR pszMetric,  
   VARIANT   varValue  
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
 [in] Název metriky.  
  
 `varValue`  
 [in] Určuje hodnotu metriky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Metrika je hodnota registru použít ke změně chování ladicího stroje nebo inzerovat podporované funkce. Tato metoda může předávat voláním příslušné formu [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) funkci `SetMetric`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)

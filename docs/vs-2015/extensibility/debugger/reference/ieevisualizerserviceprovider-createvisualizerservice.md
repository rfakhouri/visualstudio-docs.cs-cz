---
title: IEEVisualizerServiceProvider::CreateVisualizerService | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService
helpviewer_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService method
ms.assetid: f366f7c9-358d-46c8-993f-32ff86539833
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ed8327690c42f54a33209b2f0acfa45a138ec51c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68155082"
---
# <a name="ieevisualizerserviceprovidercreatevisualizerservice"></a>IEEVisualizerServiceProvider::CreateVisualizerService
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda vytvoří vizualizační službou.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateVisualizerService(  
   IDebugBinder*              binder,  
   IDebugSymbolProvider*      pSymProv,  
   IDebugAddress*             pAddress,  
   IEEVisualizerDataProvider* dataProvider,  
   IEEVisualizerService**     ppService  
);  
```  
  
```csharp  
int CreateVisualizerService(  
   IDebugBinder binder,  
   IDebugSymbolProvider      pSymProv,  
   IDebugAddress             pAddress,  
   IEEVisualizerDataProvider dataProvider,  
   out IEEVisualizerService  ppService  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `binder`  
 [in] [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) předán objekt [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md).  
  
 `pSymProv`  
 [in] [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) předán objekt `IDebugParsedExpression::EvaluateSync`.  
  
 `pAddress`  
 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) předán objekt `IDebugParsedExression::EvaluateSync`.  
  
 `dataProvider`  
 [in] Implementaci objektu [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) rozhraní (zadané ve vyhodnocovací filtr výrazů).  
  
 `ppService`  
 [out] Vytvořená služba.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 `binder`, `pSymProv`, A `pAddress` parametry byly předány do `IDebugParsedExpression::EvaluateSync` metody. `CreateVisualizerService` je možné volat pouze z `IDebugParsedExpression::EvaluateSync` jako součást podpory vyhodnocovač výrazů pro vizualizérů typů.  
  
## <a name="see-also"></a>Viz také  
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)

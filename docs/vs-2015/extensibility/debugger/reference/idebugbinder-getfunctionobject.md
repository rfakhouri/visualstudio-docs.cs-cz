---
title: IDebugBinder::GetFunctionObject | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugBinder::GetFunctionObject
helpviewer_keywords:
- IDebugBinder::GetFunctionObject method
ms.assetid: 8fb789df-8f30-420d-8ca5-bb496a6738f1
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 901b1f046acf8d57d34bc2ce541dd944994626f8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672473"
---
# <a name="idebugbindergetfunctionobject"></a>IDebugBinder::GetFunctionObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugBinder::GetFunctionObject](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder-getfunctionobject).  
  
Tato metoda načte [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) objekt použitý k vytvoření parametry funkce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetFunctionObject(   
   IDebugFunctionObject **ppFunction  
);  
```  
  
```csharp  
int GetFunctionObject(  
   out IDebugFunctionObject ppFunction  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppFunction`  
 [out] Vrátí [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní, které se používá k vytvoření parametry funkce.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)


---
title: IDebugExpressionEvaluationCompleteEvent2::GetResult | Dokumentace Microsoftu
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
- IDebugExpressionEvaluationCompleteEvent2::GetResult
helpviewer_keywords:
- IDebugExpressionEvaluationCompleteEvent2::GetResult
ms.assetid: d9ad3e22-b6b2-421e-9a43-6bb8c70d12a9
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1e9b1bf5b24a1e8b0e9ea623eb749827b2e8a988
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631582"
---
# <a name="idebugexpressionevaluationcompleteevent2getresult"></a>IDebugExpressionEvaluationCompleteEvent2::GetResult
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugExpressionEvaluationCompleteEvent2::GetResult](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult).  
  
Získá výsledek vyhodnocení výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetResult(   
   IDebugProperty2** ppResult  
);  
```  
  
```csharp  
int GetResult(   
   out IDebugProperty2 ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppResult`  
 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt, který reprezentuje výsledek vyhodnocení výrazu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vrácený [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt obsahuje hodnotu vyhodnocený výraz. Všimněte si, že tato hodnota může být složité hodnota jako například pole, ale konečný výsledek musí být číselný nebo řetězcová hodnota, která se zobrazí uživateli.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)


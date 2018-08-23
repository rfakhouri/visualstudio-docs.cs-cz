---
title: IDebugQueryEngine2::GetEngineInterface | Dokumentace Microsoftu
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
- IDebugQueryEngine2::GetEngineInterface
helpviewer_keywords:
- IDebugQueryEngine2::GetEngineInterface
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b3838155ba819a332c4b984432a19154509d7b88
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677841"
---
# <a name="idebugqueryengine2getengineinterface"></a>IDebugQueryEngine2::GetEngineInterface
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugQueryEngine2::GetEngineInterface](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugqueryengine2-getengineinterface).  
  
Získá rozhraním vlastního ladicího stroje (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetEngineInterface(   
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetEngineInterface(   
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppUnk`  
 [out] Vrátí `IUnknown` objekt představuje ladicího stroje (DE) a který může být dotázán na platná rozhraní přidružené k Zavedenými (například [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) nebo [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)).  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Výsledný rozhraní by měl použít opatrně, protože volání prostřednictvím rozhraní načíst z této metody obchází zpracování správce ladění relace a může vést k SDM převedení do špatném stavu nebo generování chyb během ladění.  
  
## <a name="see-also"></a>Viz také  
 [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)


---
title: IDebugObject::IsEqual | Dokumentace Microsoftu
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
- IDebugObject::IsEqual
helpviewer_keywords:
- IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3ed6ef6736c110864c9ec6e8762475e35e3321cc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627805"
---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugObject::IsEqual](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject-isequal).  
  
Porovná objekt s tímto objektem.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT IsEqual(   
   IDebugObject* pObject,  
   BOOL*         pfIsEqual  
);  
```  
  
```csharp  
int IsEqual(  
   IDebugObject pObject,  
   out int      pfIsEqual  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pObject`  
 [in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt představující objekt k porovnání s.  
  
 `pfIsEqual`  
 [out] Vrátí nenulovou (`TRUE`) Pokud jsou hodnoty objekty stejné; jinak, vrátí hodnotu 0 (`FALSE`).  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Obvykle tuto metodu můžete porovnat adresy hodnoty reprezentované `pObject` parametr a to [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt; Pokud adresy jsou si rovny, pak objekty lze považovat za stejné.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)


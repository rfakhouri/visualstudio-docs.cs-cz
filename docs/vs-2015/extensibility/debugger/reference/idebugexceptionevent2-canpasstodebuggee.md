---
title: IDebugExceptionEvent2::CanPassToDebuggee | Dokumentace Microsoftu
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
- IDebugExceptionEvent2::CanPassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::CanPassToDebuggee
ms.assetid: ae4bbe0a-fbe1-49be-a310-ea64279a434b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7233d6ee9b1f82d72717df9284221fca65673391
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677536"
---
# <a name="idebugexceptionevent2canpasstodebuggee"></a>IDebugExceptionEvent2::CanPassToDebuggee
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugExceptionEvent2::CanPassToDebuggee](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee).  
  
Určuje, zda ladicí stroj (DE) podporuje možnost k laděnému při provádění pokračuje programu předat tuto výjimku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT CanPassToDebuggee(  
   void  
);  
```  
  
```csharp  
int CanPassToDebuggee();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí buď `S_OK` (výjimky může být předán program) nebo `S_FALSE` (výjimky nelze předat).  
  
## <a name="remarks"></a>Poznámky  
 DE musí mít výchozí akci k předání do laděného procesu. Rozhraní IDE se může zobrazit [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) událostí a volání [pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md) metody bez volání `CanPassToDebuggee` metody. Proto je DE by měl mít výchozí případ pro předávání výjimku, nebo ne.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md)


---
title: IDebugExceptionEvent2::CanPassToDebuggee | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
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
ms.openlocfilehash: d0e9c4e315554485b31f0ea69977317502111cf2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49182278"
---
# <a name="idebugexceptionevent2canpasstodebuggee"></a>IDebugExceptionEvent2::CanPassToDebuggee
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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
 [Continue](../../../extensibility/debugger/reference/idebugprocess3-continue.md)


---
title: IDebugAsyncOperationCallBack::onComplete | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugAsyncOperationCallBack.onComplete
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugAsyncOperationCallBack::onComplete
ms.assetid: d4023f5a-41f9-4948-b0dc-3317d61bb783
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f9e5532a55901d8e29addfee58594645440991f6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62821869"
---
# <a name="idebugasyncoperationcallbackoncomplete"></a>IDebugAsyncOperationCallBack::onComplete
Signalizuje, že výsledek je k dispozici z operace asynchronní ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT onComplete();  
```  
  
#### <a name="parameters"></a>Parametry  
 Tato metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda signalizuje, že výsledek je k dispozici `IDebugAsyncOperation` objektu. Událost je aktivována v vlákno ladicího programu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugAsyncOperationCallBack Interface](../../winscript/reference/idebugasyncoperationcallback-interface.md)   
 [IDebugAsyncOperation – rozhraní](../../winscript/reference/idebugasyncoperation-interface.md)
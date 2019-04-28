---
title: IDebugApplicationThread::SynchronousCallIntoThread | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationThread.SynchronousCallIntoThread
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationThread::SynchronousCallIntoThread
ms.assetid: 8a91157f-dade-418a-ad02-5607ce12c95c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0c9b89332b55a180220820e8ffe1e030d37a848
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62822083"
---
# <a name="idebugapplicationthreadsynchronouscallintothread"></a>IDebugApplicationThread::SynchronousCallIntoThread
Poskytuje mechanismus pro volající ke spouštění kódu v vlákna aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SynchronousCallIntoThread(  
   IDebugThreadCall*  pstcb,  
   DWORD_PTR          dwParam1,  
   DWORD_PTR          dwParam2,  
   DWORD_PTR          dwParam3  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstcb`  
 [in] Objekt k volání.  
  
 `dwParam1`  
 [in] První parametr předat `IDebugThreadCall::ThreadCallHandler` metody.  
  
 `dwParam2`  
 [in] Druhý parametr předat `IDebugThreadCall::ThreadCallHandler` metody.  
  
 `dwParam3`  
 [in] Třetí parametr předat `IDebugThreadCall::ThreadCallHandler` metody.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda poskytuje mechanismus pro volající ke spouštění kódu v vlákno ladicího programu. Jazyk modulů a hostitelé obvykle tuto metodu implementace pomocí volných vláken objekty nad jejich implementace jednoho vláken.  
  
## <a name="see-also"></a>Viz také  
 [Idebugapplicationthread – rozhraní](../../winscript/reference/idebugapplicationthread-interface.md)   
 [IDebugThreadCall – rozhraní](../../winscript/reference/idebugthreadcall-interface.md)
---
title: IDebugApplication::SynchronousCallInDebuggerThread | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.SynchronousCallInDebuggerThread
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::SynchronousCallInDebuggerThread
ms.assetid: 9daa1722-f25a-4691-aefc-fd28672fb883
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5460efaa3448c7812707e0baa7b2f5afe1d27a0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62990560"
---
# <a name="idebugapplicationsynchronouscallindebuggerthread"></a>IDebugApplication::SynchronousCallInDebuggerThread
Poskytuje mechanismus pro volající ke spouštění kódu v vlákno ladicího programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SynchronousCallInDebuggerThread(  
   IDebugThreadCall*  pptc,  
   DWORD_PTR          dwParam1,  
   DWORD_PTR          dwParam2,  
   DWORD_PTR          dwParam3  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pptc`  
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
 Jazyk modulů a hostitelé obvykle tuto metodu implementace pomocí volných vláken objekty nad jejich implementace jednoho vláken.  
  
## <a name="see-also"></a>Viz také  
 [Idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md)   
 [IDebugThreadCall – rozhraní](../../winscript/reference/idebugthreadcall-interface.md)
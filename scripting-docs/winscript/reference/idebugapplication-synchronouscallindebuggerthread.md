---
title: IDebugApplication::SynchronousCallInDebuggerThread | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: b5c2a4d6c23339a396fbc367e68b81bb13c75adc
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089944"
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
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Jazyk modulů a hostitelé obvykle tuto metodu implementace pomocí volných vláken objekty nad jejich implementace jednoho vláken.  
  
## <a name="see-also"></a>Viz také  
 [Idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md)   
 [IDebugThreadCall – rozhraní](../../winscript/reference/idebugthreadcall-interface.md)
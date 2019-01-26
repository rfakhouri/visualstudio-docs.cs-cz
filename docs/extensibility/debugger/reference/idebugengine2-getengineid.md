---
title: IDebugEngine2::GetEngineID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::GetEngineID
helpviewer_keywords:
- IDebugEngine2::GetEngineID
ms.assetid: 0d5674c8-a9b9-4b72-8211-d2d68695775a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 398e4f11702afc3184fb7d081f65a99cccad0bcf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54924000"
---
# <a name="idebugengine2getengineid"></a>IDebugEngine2::GetEngineID
Získá identifikátor GUID ladicího stroje (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetEngineID(   
   GUID* pguidEngine  
);  
```  
  
```csharp  
int GetEngineID(   
   out Guid pguidEngine  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pguidEngine`  
 [out] Vrátí identifikátor GUID je DE.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tady je několik příkladů identifikátorů GUID typické `guidScriptEng`, `guidNativeEng`, nebo `guidSQLEng`. Nové ladicí stroj se vytvoří vlastní identifikátor GUID pro identifikaci.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchý `CEngine` objekt, který implementuje [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) rozhraní.  
  
```cpp  
HRESULT CEngine::GetEngineId(GUID *pguidEngine){    
   if (pguidEngine) {    
      // Set pguidEngine to guidBatEng, as defined in the Batdbg.idl file.    
      // Other languages would require their own guidDifferentEngine to be  
      //defined in the Batdbg.idl file.    
      *pguidEngine = guidBatEng;    
      return NOERROR; // This is typically S_OK.    
   } else {  
      return E_INVALIDARG;    
   }    
}    
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
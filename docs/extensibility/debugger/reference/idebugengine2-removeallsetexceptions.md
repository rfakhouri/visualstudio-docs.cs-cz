---
title: IDebugEngine2::RemoveAllSetExceptions | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::RemoveAllSetExceptions
helpviewer_keywords:
- IDebugEngine2::RemoveAllSetExceptions
ms.assetid: 165fbe89-802d-4d99-85ca-c10fd6cccc09
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e28eb35d1d6172f693cc2be0e17aa3cd25050373
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986290"
---
# <a name="idebugengine2removeallsetexceptions"></a>IDebugEngine2::RemoveAllSetExceptions
Odebere seznam výjimek, integrovaném vývojovém prostředí má nastavit pro konkrétní architekturu za běhu nebo jazyk.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT RemoveAllSetExceptions(   
   REFGUID guidType  
);  
```  
  
```csharp  
int RemoveAllSetExceptions(   
   ref Guid guidType  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidType`  
 [in] Identifikátor GUID pro jazyk nebo identifikátor GUID pro ladicí stroj, který je specifický pro architekturu za běhu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Výjimky odebrat touto metodou byly nastavené zásadami předchozích volání [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) metody.  
  
 Chcete-li odebrat určité výjimky, zavolejte [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)
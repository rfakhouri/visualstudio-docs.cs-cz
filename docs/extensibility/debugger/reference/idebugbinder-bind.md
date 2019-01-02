---
title: IDebugBinder::Bind | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBinder::Bind
helpviewer_keywords:
- IDebugBinder::Bind method
ms.assetid: 15a11ad7-0fcc-4e80-ae34-8a7dd7bae3c3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 72beca1ede38b310e34edfaabce0ee02e8fb52cc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53865203"
---
# <a name="idebugbinderbind"></a>IDebugBinder::Bind
Tato metoda načte místní paměti nebo objekt, který obsahuje aktuální hodnotu tohoto symbolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Bind(   
   IDebugObject*  pContainer,  
   IDebugField*   pField,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Bind(  
   IDebugObject     pContainer,  
   IDebugField      pField,  
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pContainer`  
 [in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) , která obsahuje podřízené odkazuje `pField`.  
  
 `pField`  
 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) představující symbol.  
  
 `ppObject`  
 [out] Vrátí `IDebugObject` , která představuje výskyt symbolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
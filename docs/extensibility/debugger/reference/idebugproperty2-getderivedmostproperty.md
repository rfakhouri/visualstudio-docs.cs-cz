---
title: IDebugProperty2::GetDerivedMostProperty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::GetDerivedMostProperty
helpviewer_keywords:
- IDebugProperty2::GetDerivedMostProperty
ms.assetid: cc86b461-62d1-4340-8209-c65037fd8b02
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2c2a895e73393739fc2aa6c44d809647c9ccbb3b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53988132"
---
# <a name="idebugproperty2getderivedmostproperty"></a>IDebugProperty2::GetDerivedMostProperty
Získá vlastnost nejvíce odvozené vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDerivedMostProperty (   
   IDebugProperty2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostProperty (   
   out IDebugProperty2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppDerivedMost`  
 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt, který reprezentuje vlastnost nejvíce odvozené.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `S_GETDERIVEDMOST_NO_DERIVED_MOST` Pokud není žádná vlastnost odvozené většinu k načtení.  
  
## <a name="remarks"></a>Poznámky  
 Například, pokud je tato vlastnost popisuje objekt, který implementuje `ClassRoot` , ale která je ve skutečnosti instance `ClassDerived` , která je odvozena od `ClassRoot`, pak tato metoda vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objektu popisující `ClassDerived` objektu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
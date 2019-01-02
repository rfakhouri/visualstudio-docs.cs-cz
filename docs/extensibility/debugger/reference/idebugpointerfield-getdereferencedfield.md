---
title: IDebugPointerField::GetDereferencedField | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPointerField::GetDereferencedField
helpviewer_keywords:
- IDebugPointerField::GetDereferencedField method
ms.assetid: 8de988ab-cd79-4287-be72-3c900f2fe407
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 58f590f88344a76095156b71c4c535b158582dc3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53844593"
---
# <a name="idebugpointerfieldgetdereferencedfield"></a>IDebugPointerField::GetDereferencedField
Tato metoda vrátí typ objektu, na kterou odkazuje tento objekt ukazatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDereferencedField(  
   IDebugField** ppField  
);  
```  
  
```csharp  
int GetDereferencedField(  
   out IDebugField ppField  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppField`  
 [out] Vrátí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) popisující typ cílového objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud například [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md) objektu odkazuje na celé číslo, [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) typ vrácený touto metodou popisuje typu celé číslo.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
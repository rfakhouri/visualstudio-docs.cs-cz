---
title: IDebugPointerField::GetDereferencedField | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 77af1428dbdd0ea9f84000bda34ea8608b17cc24
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugpointerfieldgetdereferencedfield"></a>IDebugPointerField::GetDereferencedField
Tato metoda vrátí typ objektu, na kterou odkazuje tento ukazatel objekt.  
  
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
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud například [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md) objekt odkazuje na celé číslo, [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) typ tato metoda vrátí popisuje typu celé číslo.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
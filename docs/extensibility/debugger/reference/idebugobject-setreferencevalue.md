---
title: IDebugObject::SetReferenceValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::SetReferenceValue
helpviewer_keywords:
- IDebugObject::SetReferenceValue method
ms.assetid: 08c78a4e-98eb-41cb-8b75-02a6a43d49f7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8941b09a18968fccba72c6e03a2fe612234909d5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugobjectsetreferencevalue"></a>IDebugObject::SetReferenceValue
Nastaví hodnotu odkaz na tento objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetReferenceValue(   
   IDebugObject* pObject  
);  
```  
  
```csharp  
int SetReferenceValue(  
   [In] IDebugObject pObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pObject`  
 [v] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objektu, který představuje novou hodnotu odkazu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je tato [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objektu odkaz na hodnotu zadanou v objektu `pObject` parametr vyvolání rychle jakékoli předchozí odkaz. Poznámka: Tento to `IDebugObject` objektu už musí být odkazového typu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)
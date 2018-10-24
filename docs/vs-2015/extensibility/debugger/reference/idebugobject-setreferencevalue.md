---
title: IDebugObject::SetReferenceValue | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugObject::SetReferenceValue
helpviewer_keywords:
- IDebugObject::SetReferenceValue method
ms.assetid: 08c78a4e-98eb-41cb-8b75-02a6a43d49f7
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2289b06eb150d71c4078bcecde31697d6742fd43
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49813269"
---
# <a name="idebugobjectsetreferencevalue"></a>IDebugObject::SetReferenceValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nastaví odkaz na hodnotu tohoto objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt představující novou hodnotu odkazu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda provádí to [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) odkazu na hodnotu objektu, který je uveden v objektu `pObject` parametr odhazuje všechny předchozí odkazy. Všimněte si, že tento `IDebugObject` objekt již musí být typ odkazu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)


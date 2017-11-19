---
title: IDebugBinder::Bind | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBinder::Bind
helpviewer_keywords: IDebugBinder::Bind method
ms.assetid: 15a11ad7-0fcc-4e80-ae34-8a7dd7bae3c3
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: db8465a0f1eefe94482020acc8788da84f05b424
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugbinderbind"></a>IDebugBinder::Bind
Tato metoda získá kontext paměti nebo objekt, který obsahuje aktuální hodnotu symbolu.  
  
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
 [v] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) obsahující podřízené odkazuje `pField`.  
  
 `pField`  
 [v] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) představující symbolu.  
  
 `ppObject`  
 [out] Vrátí `IDebugObject` představující instanci symbolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
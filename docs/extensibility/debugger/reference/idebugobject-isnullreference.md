---
title: IDebugObject::IsNullReference | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::IsNullReference
helpviewer_keywords:
- IDebugObject::IsNullReference method
ms.assetid: 6dbfcdb0-954f-4486-8fac-7ea8d003e3a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1a886bf56cfafc615099aa489f9d329229ea8727
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugobjectisnullreference"></a>IDebugObject::IsNullReference
Ověřuje, zda tento objekt je odkaz s hodnotou null.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT IsNullReference(   
   BOOL* pfIsNull  
);  
```  
  
```csharp  
int IsNullReference(  
   out int pfIsNull  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pfIsNull`  
 [out] Vrátí nenulový (`TRUE`) Pokud tento objekt je odkaz s hodnotou null; jinak vrátí hodnotu 0 (`FALSE`).  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Odkaz s hodnotou null znamená prázdný objekt nebo objekt, který nebyl přiřazen.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
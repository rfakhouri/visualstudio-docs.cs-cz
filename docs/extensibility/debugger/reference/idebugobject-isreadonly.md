---
title: IDebugObject::IsReadOnly | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugObject::IsReadOnly
helpviewer_keywords:
- IDebugObject::IsReadOnly method
ms.assetid: c460f772-d08a-4b36-81f3-dff6a51a93fd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5920e4804218d97c51ef7477f31a90556e8c7a3a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53956033"
---
# <a name="idebugobjectisreadonly"></a>IDebugObject::IsReadOnly
Určuje, zda tento objekt je jen pro čtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT IsReadOnly(   
   BOOL* pfIsReadOnly  
);  
```  
  
```csharp  
int IsReadOnly(  
   out int pfIsReadOnly  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pfIsReadOnly`  
 [out] Vrátí nenulovou (`TRUE`) Pokud tento objekt je jen pro čtení; jinak vrátí hodnotu, vrátí hodnotu 0 (`FALSE`).  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Objekt jen pro čtení nemůže mít hodnotu po jeho vytvoření změnit.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
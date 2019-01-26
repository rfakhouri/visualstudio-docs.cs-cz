---
title: IDebugObject::IsNullReference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugObject::IsNullReference
helpviewer_keywords:
- IDebugObject::IsNullReference method
ms.assetid: 6dbfcdb0-954f-4486-8fac-7ea8d003e3a9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 021d7d8b7c1203aab68a93efe8581f66dec698f9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54975267"
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
 [out] Vrátí nenulovou (`TRUE`) Pokud tento objekt je odkaz s hodnotou null; v opačném případě vrátí hodnotu 0 (`FALSE`).  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Odkaz s hodnotou null znamená, že prázdný objekt nebo objekt, který nebyl přiřazen.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
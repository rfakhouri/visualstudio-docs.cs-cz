---
title: IDebugExtendedField::IsClosedType | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IsClosedType
- IDebugExtendedField::IsClosedType
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6b3c1badda9933c97761d3bf209380ba0c822b7f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55002792"
---
# <a name="idebugextendedfieldisclosedtype"></a>IDebugExtendedField::IsClosedType
Určuje, zda pole představuje uzavřený typ.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT IsClosedType(  
   void  
);  
```  
  
```csharp  
int IsClosedType();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je pole uzavřený typ, vrátí `S_OK`; v opačném případě vrátí `S_FALSE`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)
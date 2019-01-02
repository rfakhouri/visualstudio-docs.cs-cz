---
title: REFERENCE_TYPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- REFERENCE_TYPE
helpviewer_keywords:
- REFERENCE_TYPE enumeration
ms.assetid: b1ffba10-eb9d-48ba-bf48-6d8b71d6f270
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 38234a2c1e2bdc7e0f3e51a25642e7372bec968a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53964582"
---
# <a name="referencetype"></a>REFERENCE_TYPE
Určuje typ odkazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_REFERENCE_TYPE {   
   REF_TYPE_WEAK   = 0x0001,  
   REF_TYPE_STRONG = 0x0002  
};  
typedef DWORD REFERENCE_TYPE;  
```  
  
```csharp  
public enum enum_REFERENCE_TYPE {   
   REF_TYPE_WEAK   = 0x0001,  
   REF_TYPE_STRONG = 0x0002  
};  
```  
  
## <a name="members"></a>Členové  
 REF_TYPE_WEAK  
 Určuje nestálý odkaz. Nelze kombinovat s `REF_TYPE_STRONG`.  
  
 REF_TYPE_STRONG  
 Určuje silného odkazu. Nelze kombinovat s `REF_TYPE_WEAK`.  
  
## <a name="remarks"></a>Poznámky  
 Použít jako `dwRefType` člena [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury.  
  
 Předán jako parametr [SetReferenceType](../../../extensibility/debugger/reference/idebugreference2-setreferencetype.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [SetReferenceType](../../../extensibility/debugger/reference/idebugreference2-setreferencetype.md)
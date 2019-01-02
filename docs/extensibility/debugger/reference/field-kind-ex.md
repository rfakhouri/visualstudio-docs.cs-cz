---
title: FIELD_KIND_EX | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- FIELD_KIND_EX enumeration
ms.assetid: 922c3208-1e94-485f-b70a-3bc96affeff8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b6954aaf92c5d77ad4d8f51e6b342bfc021b37a7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53870872"
---
# <a name="fieldkindex"></a>FIELD_KIND_EX
Vytvoří výčet další typy polí, která [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt může obsahovat. Tento výčet rozšiřuje [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_FIELD_KIND_EX  
{  
   FIELD_KIND_EX_NONE = 0,  
   FIELD_TYPE_EX_METHODVAR = 0x1,  
   FIELD_TYPE_EX_CLASSVAR = 0x2  
} ;  
typedef DWORD FIELD_KIND_EX;  
```  
  
```csharp  
public enum enum_FIELD_KIND_EX  
{  
   FIELD_KIND_EX_NONE = 0,  
   FIELD_TYPE_EX_METHODVAR = 0x1,  
   FIELD_TYPE_EX_CLASSVAR = 0x2  
};  
```  
  
## <a name="members"></a>Členové  
 FIELD_KIND_EX_NONE  
 Pole neobsahuje rozšířeného typu.  
  
 FIELD_TYPE_EX_METHODVAR  
 Pole obsahuje proměnnou metody.  
  
 FIELD_TYPE_EX_CLASSVAR  
 Pole obsahuje proměnné třídy.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: SH.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)
---
title: STEPUNIT | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- STEPUNIT
helpviewer_keywords:
- STEPUNIT enumeration
ms.assetid: cb8441f2-f744-4e73-acfe-ae8542df9649
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d97f4f065d48b2b9c56bf029fb944eb3e4e7cb11
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414594"
---
# <a name="stepunit"></a>STEPUNIT
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje jednotku kroku pro procházení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_STEPUNIT {   
   STEP_STATEMENT   = 0,  
   STEP_LINE        = 1,  
   STEP_INSTRUCTION = 2  
};  
typedef DWORD STEPUNIT;  
```  
  
```csharp  
enum enum_STEPUNIT {   
   STEP_STATEMENT   = 0,  
   STEP_LINE        = 1,  
   STEP_INSTRUCTION = 2  
};  
```  
  
## <a name="members"></a>Členové  
 STEP_STATEMENT  
 Kroky příkazem.  
  
 STEP_LINE  
 Kroky po řádku.  
  
 STEP_INSTRUCTION  
 Kroky podle instrukce.  
  
## <a name="remarks"></a>Poznámky  
 Předán jako argument [krok](../../../extensibility/debugger/reference/idebugprocess3-step.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Step](../../../extensibility/debugger/reference/idebugprocess3-step.md)

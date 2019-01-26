---
title: CONTEXT_COMPARE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CONTEXT_COMPARE
helpviewer_keywords:
- CONTEXT_COMPARE enumeration
ms.assetid: 701ed61c-a320-4c20-a335-0b840024abc0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 95706df8b9b4d366e8baf25a96e3e15bc6532be1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54930209"
---
# <a name="contextcompare"></a>CONTEXT_COMPARE
Určuje kritéria pro porovnání dvou kontextů paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_CONTEXT_COMPARE {   
   CONTEXT_EQUAL                 = 0x0001,  
   CONTEXT_LESS_THAN             = 0x0002,  
   CONTEXT_GREATER_THAN          = 0x0003,  
   CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,  
   CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,  
   CONTEXT_SAME_SCOPE            = 0x0006,  
   CONTEXT_SAME_FUNCTION         = 0x0007,  
   CONTEXT_SAME_MODULE           = 0x0008,  
   CONTEXT_SAME_PROCESS          = 0x0009  
};  
typedef DWORD CONTEXT_COMPARE;  
```  
  
```csharp  
public enum enum_CONTEXT_COMPARE {   
   CONTEXT_EQUAL                 = 0x0001,  
   CONTEXT_LESS_THAN             = 0x0002,  
   CONTEXT_GREATER_THAN          = 0x0003,  
   CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,  
   CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,  
   CONTEXT_SAME_SCOPE            = 0x0006,  
   CONTEXT_SAME_FUNCTION         = 0x0007,  
   CONTEXT_SAME_MODULE           = 0x0008,  
   CONTEXT_SAME_PROCESS          = 0x0009  
};  
```  
  
## <a name="members"></a>Členové  
 CONTEXT_EQUAL  
 Vyhledá první kontext paměti v seznamu, který je roven cílový kontext paměti.  
  
 CONTEXT_LESS_THAN  
 Vyhledá první kontext paměti v seznamu, která je menší než cílový kontext paměti.  
  
 CONTEXT_GREATER_THAN  
 Vyhledá první kontext paměti v seznamu, která je větší než cílový kontext paměti.  
  
 CONTEXT_LESS_THAN_OR_EQUAL  
 Vyhledá první kontext paměti v seznamu, která je menší než nebo rovna hodnotě cílový kontext paměti.  
  
 CONTEXT_GREATER_THAN_OR_EQUAL  
 Najdete první paměťové oblasti v seznamu, který je větší než nebo rovna hodnotě cílový kontext paměti.  
  
 CONTEXT_SAME_SCOPE  
 Vyhledá první kontext paměti v seznamu, který je ve stejném oboru jako cílový kontext paměti.  
  
 CONTEXT_SAME_FUNCTION  
 Najdete první paměťové oblasti v seznamu, který je ve stejné funkci jako cílový obor paměti.  
  
 CONTEXT_SAME_MODULE  
 Vyhledá první kontext paměti v seznamu, který je ve stejném modulu jako cílový kontext paměti.  
  
 CONTEXT_SAME_PROCESS  
 Vyhledá první kontext paměti v seznamu, který je ve stejném procesu jako cílový kontext paměti.  
  
## <a name="remarks"></a>Poznámky  
 Předán jako argument [porovnání](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md) metody.  
  
 Tyto hodnoty se používají k vyhledání prvního kontextu paměti v seznamu, který splňuje zadané porovnávací kritéria. Kontext paměti je uveden seznam kontexty paměti se porovnat proti prostřednictvím `IDebugMemoryContext2::Compare` metody. První kontext paměti v seznamu, pro který je operátor porovnání `true` je poté vrácen.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)
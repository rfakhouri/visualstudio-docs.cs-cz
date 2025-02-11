---
title: CONTEXT_COMPARE | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- CONTEXT_COMPARE
helpviewer_keywords:
- CONTEXT_COMPARE enumeration
ms.assetid: 701ed61c-a320-4c20-a335-0b840024abc0
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a9cf283cf7239b5ed74e38ca534538a286a477c2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68179974"
---
# <a name="contextcompare"></a>CONTEXT_COMPARE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje kritéria pro porovnání dvou kontextů paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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

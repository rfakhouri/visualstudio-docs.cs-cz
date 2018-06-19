---
title: CONTEXT_COMPARE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- CONTEXT_COMPARE
helpviewer_keywords:
- CONTEXT_COMPARE enumeration
ms.assetid: 701ed61c-a320-4c20-a335-0b840024abc0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0563f037f77c18cc5e686c1ea6acf429c91ad06d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108580"
---
# <a name="contextcompare"></a>CONTEXT_COMPARE
Určuje kritéria pro porovnání dvou kontextů paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_CONTEXT_COMPARE {   
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
public enum enum_CONTEXT_COMPARE {   
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
 Najít první kontextu paměti v seznamu, který se rovná cílový kontext paměti.  
  
 CONTEXT_LESS_THAN  
 Najít první kontextu paměti v seznamu, která je menší, než cílový kontext paměti.  
  
 CONTEXT_GREATER_THAN  
 Najít první kontextu paměti v seznamu, který je větší než cílový kontext paměti.  
  
 CONTEXT_LESS_THAN_OR_EQUAL  
 Najít první kontextu paměti v seznamu, která je menší než nebo rovno cílový kontext paměti.  
  
 CONTEXT_GREATER_THAN_OR_EQUAL  
 Najít první kontextu paměti v seznamu, který je větší než nebo rovno cílový kontext paměti.  
  
 CONTEXT_SAME_SCOPE  
 Najít první kontextu paměti v seznamu, který je ve stejném oboru jako cílový kontext paměti.  
  
 CONTEXT_SAME_FUNCTION  
 Najít první kontextu paměti v seznamu, který je ve stejné funkce jako cílový obor paměti.  
  
 CONTEXT_SAME_MODULE  
 Najít první kontextu paměti v seznamu, který je ve stejném modulu jako cílový kontext paměti.  
  
 CONTEXT_SAME_PROCESS  
 Najít první kontextu paměti v seznamu, který je v rámci jednoho procesu jako cílový kontext paměti.  
  
## <a name="remarks"></a>Poznámky  
 Předat jako argument k [porovnat](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md) metoda.  
  
 Tyto hodnoty se používají k vyhledání prvního kontextu paměti v seznamu, která splňuje kritéria zadaná porovnání. Kontext paměti je uveden seznam kontexty paměti se porovnat proti prostřednictvím `IDebugMemoryContext2::Compare` metoda. Kontext paměti první v seznamu, pro který relační operátor `true` je pak vrácen.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Porovnání](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)
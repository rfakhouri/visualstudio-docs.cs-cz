---
title: DOCCONTEXT_COMPARE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 966d31889d7979732af20f5e3f95546e87af6598
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103650"
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
Určuje kritéria pro porovnání dvou kontextů dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```csharp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## <a name="members"></a>Členové  
 DOCCONTEXT_EQUAL  
 Najít první kontextu dokument v seznamu, který se rovná cílový kontext dokumentu.  
  
 DOCCONTEXT_LESS_THAN  
 Najít první kontextu dokument v seznamu, která je menší, než cílový kontext dokumentu.  
  
 DOCCONTEXT_GREATER_THAN  
 Najít první kontextu dokument v seznamu, který je větší než cílový kontext dokumentu.  
  
 DOCCONTEXT_SAME_DOCUMENT  
 Najít první kontextu dokument v seznamu, který je ve stejném dokumentu jako cílový kontext dokumentu.  
  
## <a name="remarks"></a>Poznámky  
 Předat jako argument k [porovnat](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) metoda.  
  
 Tyto hodnoty se používají k určení kritérií porovnání pro hledání kontext první dokument v seznamu. Kontext dokumentu je uveden seznam kontexty dokumentu se porovnat proti prostřednictvím `IDebugDocumentContext2::Compare` metoda. Kontext první dokument v seznamu, pro který relační operátor `true` je pak vrácen.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Porovnání](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)
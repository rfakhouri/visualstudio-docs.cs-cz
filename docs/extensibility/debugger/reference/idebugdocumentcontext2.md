---
title: IDebugDocumentContext2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDocumentContext2
helpviewer_keywords:
- IDebugDocumentContext2
ms.assetid: 2a446c71-8100-4c09-a1cc-fd446bd74030
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dca62a511cd247f3344e319a7c3b4946b848103f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53909695"
---
# <a name="idebugdocumentcontext2"></a>IDebugDocumentContext2
Toto rozhraní představuje pozici ve zdrojovém souboru dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní jako součást své podpory úrovně ladění zdrojového kódu. Kromě pozice ve zdrojovém kódu toto rozhraní poskytuje metody pro porovnávání kontextů a procházení jako zdrojový kód.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Metody v několika rozhraní, obvykle [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) a [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) rozhraní, vrátit toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugDocumentContext2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)|Získá dokument, který obsahuje tento kontext dokumentu.|  
|[GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)|Získá zobrazitelný název dokumentu, který obsahuje tento kontext dokumentu.|  
|[EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)|Načte seznam všech kontextech kód spojený s tímto kontextem dokumentu.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugdocumentcontext2-getlanguageinfo.md)|Získá jazyk spojený s tímto kontextem dokumentu.|  
|[GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|Získá rozsah souboru příkazů tohoto kontextu dokumentu.|  
|[GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)|Získá zdrojový rozsah souboru tohoto kontextu dokumentu.|  
|[Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)|Porovná tento kontext dokumentu do daného pole kontextů dokumentu.|  
|[Seek](../../../extensibility/debugger/reference/idebugdocumentcontext2-seek.md)|Přesune kontext dokumentu stanovený počet příkazů nebo řádky.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)
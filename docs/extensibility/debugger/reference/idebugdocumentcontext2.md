---
title: IDebugDocumentContext2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentContext2
helpviewer_keywords: IDebugDocumentContext2
ms.assetid: 2a446c71-8100-4c09-a1cc-fd446bd74030
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9a679fcd597251e5e76a1d3457b5cfe54e5caecb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdocumentcontext2"></a>IDebugDocumentContext2
Toto rozhraní představuje pozici ve zdrojovém souboru dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní jako součást jeho podpora pro úrovně ladění zdrojového kódu. Toto rozhraní kromě pozici ve zdrojovém kódu, poskytuje metody pro porovnání kontexty a procházení jako zdrojový kód.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Některé metody rozhraní, obvykle [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) a [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) rozhraní, vrátí tato rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugDocumentContext2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)|Získá dokument, který obsahuje tento kontext dokumentu.|  
|[GetName –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)|Získá zobrazitelné název dokumentu, který obsahuje tento kontext dokumentu.|  
|[EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)|Načte seznam všech kontextů kód spojený s tímto kontextem dokumentu.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugdocumentcontext2-getlanguageinfo.md)|Získá jazyk spojený s tímto kontextem dokumentu.|  
|[GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|Získá soubor příkaz rozsahu tohoto kontextu dokumentu.|  
|[Getsourcerange –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)|Získá rozsah zdrojových souborů tohoto kontextu dokumentu.|  
|[Porovnání](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)|Porovná tento dokument kontext pro dané pole kontextů dokumentu.|  
|[Hledat](../../../extensibility/debugger/reference/idebugdocumentcontext2-seek.md)|Přesune kontext dokumentu o zadaný počet příkazy nebo řádky.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)
---
title: IDebugDocument2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocument2
helpviewer_keywords: IDebugDocument2 interface
ms.assetid: 1bc58426-dbf5-4471-9aad-9d66cd80eef0
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 175be5f50b03573b13df8a8c0d2a9a0e1e921cc7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocument2"></a>IDebugDocument2
Toto rozhraní představuje zdrojový dokument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocument2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]obvykle toto rozhraní implementuje. Modul ladění (DE) můžete také implementovat toto rozhraní je nutné ho zadat zdrojový kód a zdroj neexistuje na disku.  V takových případech by také implementovat DE [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) a [IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md) rozhraní, jakož i některé další metody na [ IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) a [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Metody `IDebugDocumentContext2`, `IDebugDisassemblyStream2`, `IDebugDocumentPosition2`, a `IDebugActivateDocumentEvent2` rozhraní vrátit toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugDocument2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetName –](../../../extensibility/debugger/reference/idebugdocument2-getname.md)|Získá název dokumentu v jednom z několika formulářů.|  
|[GetDocumentClassID](../../../extensibility/debugger/reference/idebugdocument2-getdocumentclassid.md)|Získá identifikátor třídy dokumentu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je implementováno jenom v případě, že je DE poskytuje zdrojového kódu. Například při ladění skriptu na stránku HTML, je DE poskytuje zdrojový kód protože stažením nebo zdroj je generována dynamicky a neexistuje jako soubor na disku. Při ladění tradiční jazyky, jako je C++, není potřeba toto rozhraní implementovat.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)
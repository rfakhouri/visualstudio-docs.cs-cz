---
title: IDebugDocumentPosition2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugDocumentPosition2
helpviewer_keywords:
- IDebugDocumentPosition2 interface
ms.assetid: 0e838ced-12bb-4efc-b811-2b7c034b77b0
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ba9aaf9b0d23aed99397a6c52ca443a9477bc20a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentposition2"></a>IDebugDocumentPosition2
Toto rozhraní představuje abstraktní pozici ve zdrojovém souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio obvykle toto rozhraní implementuje. Modul ladění (DE) by také implementovat toto rozhraní, pokud je nutné zadat vlastní zdrojový kód (jako když je DE implementuje [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je předána jako argument k [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md). Rovněž je zadán jako součást [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) – typ union (konkrétně [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) struktura), je zase součástí [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) struktura, který se používá při vytváření čekající zarážky.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugDocumentPosition2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetFileName](../../../extensibility/debugger/reference/idebugdocumentposition2-getfilename.md)|Získá název souboru zdrojového souboru, který obsahuje tento dokument pozice.|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)|Získá obsahující dokumentu.|  
|[IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)|Určuje, pokud tato pozice je součástí daného dokumentu.|  
|[Getrange –](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)|Získá rozsahu pro tuto pozici dokumentu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)
---
title: IDebugDocumentPosition2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDocumentPosition2
helpviewer_keywords:
- IDebugDocumentPosition2 interface
ms.assetid: 0e838ced-12bb-4efc-b811-2b7c034b77b0
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5398d94733bf2ae4c5fe82daa4df0839857b72a6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68200245"
---
# <a name="idebugdocumentposition2"></a>IDebugDocumentPosition2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní představuje abstraktní pozice ve zdrojovém souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio obvykle implementuje toto rozhraní. Ladicí stroj (DE) by také implementovat toto rozhraní, pokud je nutné zadat vlastní zdrojového kódu (jako při DE implementuje [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je předán jako argument [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md). Je rovněž dodán jako součást [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) sjednocení (konkrétně [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) struktury), který je zase součástí [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) strukturu, který se používá při vytváření čekající zarážkou.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugDocumentPosition2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetFileName](../../../extensibility/debugger/reference/idebugdocumentposition2-getfilename.md)|Získá název souboru zdrojového souboru, který obsahuje pozici tohoto dokumentu.|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)|Získá aktuálního dokumentu.|  
|[IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)|Určuje, pokud toto umístění je součástí daného dokumentu.|  
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)|Získá rozsah pro tuto pozici dokumentu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)

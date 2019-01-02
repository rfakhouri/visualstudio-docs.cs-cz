---
title: IDebugDocumentText2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDocumentText2
helpviewer_keywords:
- IDebugDocumentText2 interface
ms.assetid: e85f50a3-211c-4220-a9f4-789950ba2782
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cae0bfefe4ab39d42f9cc67080d17394b1a1418b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53838421"
---
# <a name="idebugdocumenttext2"></a>IDebugDocumentText2
Toto rozhraní představuje textový dokument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentText2 : IDebugDocument2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní, pokud je zdrojový kód, je potřeba zadat v textové podobě. Protože toto je nejčastější případ, pokud se Zavedenými implementuje [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní, měl by také implementovat `IDebugDocumentText2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití `QueryInterface` metodu k získání tohoto rozhraní ze `IDebugDocument2` rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na `IDebugDocument2` rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetSize](../../../extensibility/debugger/reference/idebugdocumenttext2-getsize.md)|Získá velikost textu na této pozici v dokumentu.|  
|[GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)|Získá text ze zadaného umístění v dokumentu.|  
  
## <a name="remarks"></a>Poznámky  
 Musí také implementovat objekt, který implementuje toto rozhraní <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> rozhraní, které poskytuje <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> rozhraní pro [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md) objektu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)
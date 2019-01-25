---
title: IDebugDocumentText2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDocumentText2
helpviewer_keywords:
- IDebugDocumentText2 interface
ms.assetid: e85f50a3-211c-4220-a9f4-789950ba2782
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2e81aaccd3af692f4a7e0f708685dbea4a44d5c6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54797844"
---
# <a name="idebugdocumenttext2"></a>IDebugDocumentText2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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

---
title: IDebugActivateDocumentEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugActivateDocumentEvent2
helpviewer_keywords: IDebugActivateDocumentEvent2 interface
ms.assetid: 6f37edd7-a48c-4b41-b160-dff9be63a284
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f21648f9b019fbb765290d969b1a6c68fe5ce2f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugactivatedocumentevent2"></a>IDebugActivateDocumentEvent2
Modul ladění (DE) používá toto rozhraní k vyžádání dokument se jej načíst.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugActivateDocumentEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE toto rozhraní implementuje, když potřebuje zdrojový soubor otevřít. Toto rozhraní je implementováno pouze pomocí ladění strojů, které pracovat nebo jsou součástí překladače skriptu. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní (SDM používá [QueryInterface](/cpp/atl/queryinterface) pro přístup k `IDebugEvent2` rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt událost, když potřebuje mít zdrojový soubor otevřít. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) poskytl SDM, pokud je připojené k programu laděné funkce zpětného volání.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugActivateDocumentEvent2`.  
  
|Metody|Popis|  
|-------------|-----------------|  
|[GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)|Získá dokument, který chcete aktivovat.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocumentcontext.md)|Získá kontext dokumentu, která popisuje pozici v tomto dokumentu.|  
  
## <a name="remarks"></a>Poznámky  
 Typický scénář, ve kterém se používá toto rozhraní je, že pokud se v kód skriptu na stránce HTML dojde k chybě analýzy, skript DE odešle toto rozhraní SDM tak, aby došlo k chybě analýzy dokumentu lze zobrazit.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
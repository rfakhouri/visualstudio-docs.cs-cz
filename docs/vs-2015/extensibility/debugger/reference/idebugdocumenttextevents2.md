---
title: IDebugDocumentTextEvents2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDocumentTextEvents2
helpviewer_keywords:
- IDebugDocumentTextEvents2 interface
ms.assetid: a10cbb6b-11a8-4056-b42a-2ecebf0e690d
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b574ae45dafed11ed28047859676524054951512
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65678971"
---
# <a name="idebugdocumenttextevents2"></a>IDebugDocumentTextEvents2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní se používá k upozornění na změny ve zdrojovém dokumentu, která se dodávají pomocí ladicího stroje sady Visual Studio.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentTextEvents2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní pro podporu změn ke zdrojovému kódu. Toto rozhraní je implementováno obvykle na stejný objekt, který implementuje [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] získá toto rozhraní přímo pomocí volání <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> metody. <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> Rozhraní se získá z volání <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.EnumConnectionPoints%2A> metody. <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> Rozhraní je získán voláním [QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) metodu [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugDocumentTextEvents2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[onDestroy](../../../extensibility/debugger/reference/idebugdocumenttextevents2-ondestroy.md)|Označuje, že došlo ke zničení celý dokument.|  
|[onInsertText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-oninserttext.md)|Upozorní balíček ladění, že byl vložen text do dokumentu.|  
|[onRemoveText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onremovetext.md)|Upozorní balíček ladění, že text byl odebrán z dokumentu.|  
|[onReplaceText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onreplacetext.md)|Upozorní balíček ladění, text se nahradil v dokumentu.|  
|[onUpdateTextAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatetextattributes.md)|Upozorní balíček ladění, aby byly aktualizovány atributy textu v dokumentu.|  
|[onUpdateDocumentAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatedocumentattributes.md)|Upozorní příjemce události, aby se aktualizovaly atributy dokumentu.|  
  
## <a name="remarks"></a>Poznámky  
 Pouze ladicími stroji, které poskytují své vlastní dokumenty by využít výhod `IDebugDocumentTextEvent2` rozhraní. Příklad tohoto by skriptovací stroj ladění. Právě interpretace skripty, nový zdrojový kód lze generovat se nenachází v žádném souboru disku, který znáte jenom DE.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)

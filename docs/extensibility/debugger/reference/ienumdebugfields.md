---
title: IEnumDebugFields | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFields
helpviewer_keywords: IEnumDebugFields interface
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9e930a9e78fb1d91bc5738256e0555f3949829c5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugfields"></a>IEnumDebugFields
Toto rozhraní představuje kolekci objektů implementace [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugFields : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno modulem symbol poskytovatele za účelem poskytnutí sady objektů, které implementují [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní. Všimněte si, že to není na standardní výčet COM z důvodu přítomnosti [GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md) metoda.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je vrácen rutinou [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md) a [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní implementuje následujících metod.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|Načte další sadu [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekty z výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|Přeskočí zadaný počet položek.|  
|[Resetování](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|Obnoví výčtu první položce.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|Načte kopii do aktuálního výčtu.|  
|[GetCount –](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|Načte počet položek ve výčtu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Zprostředkovatel rozhraní symbol](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)   
 [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)
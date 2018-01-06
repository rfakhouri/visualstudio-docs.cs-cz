---
title: IEnumDebugAddresses | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugAddresses
helpviewer_keywords: IEnumDebugAddresses interface
ms.assetid: 5f6f6751-e6d8-4c5a-8e81-414b6e5d8cc5
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 839d6d23e358cc3a35085d90abfa2efae11b22eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugaddresses"></a>IEnumDebugAddresses
Toto rozhraní představuje kolekci objektů implementace [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugAdresses : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno modulem symbol poskytovatele za účelem poskytnutí sady objektů, které implementují [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní. Všimněte si, že to není na standardní výčet COM z důvodu přítomnosti [GetCount](../../../extensibility/debugger/reference/ienumdebugaddresses-getcount.md) metoda.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je vrácen rutinou [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md) a [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní implementuje následujících metod.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugaddresses-next.md)|Načte další sadu [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objekty z výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugaddresses-skip.md)|Přeskočí zadaný počet položek.|  
|[Resetování](../../../extensibility/debugger/reference/ienumdebugaddresses-reset.md)|Obnoví výčtu první položce.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugaddresses-clone.md)|Načte kopii do aktuálního výčtu.|  
|[GetCount –](../../../extensibility/debugger/reference/ienumdebugaddresses-getcount.md)|Načte počet položek ve výčtu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní se obvykle používá modul ladění, které vám pomohou určit příslušnou adresu k vyhodnocení výrazu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Zprostředkovatel rozhraní symbol](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)
---
title: IEnumDebugAddresses | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugAddresses
helpviewer_keywords:
- IEnumDebugAddresses interface
ms.assetid: 5f6f6751-e6d8-4c5a-8e81-414b6e5d8cc5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0b4dc67d421928bb9c962650dcad4a1c385665a9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55027721"
---
# <a name="ienumdebugaddresses"></a>IEnumDebugAddresses
Představuje kolekci objektů implementace tohoto rozhraní [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugAdresses : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno symbol poskytovatele za účelem poskytnutí sady objektů, které implementují [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní. Všimněte si, že to není standardní výčet COM z důvodu přítomnosti [GetCount](../../../extensibility/debugger/reference/ienumdebugaddresses-getcount.md) metody.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je vrácený [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md) a [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní implementuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugaddresses-next.md)|Načte další sadu [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objekty z výčtu.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugaddresses-skip.md)|Vynechá zadaný počet položek.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugaddresses-reset.md)|Obnoví výčtu první položka.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugaddresses-clone.md)|Načte kopii do aktuálního výčtu.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugaddresses-getcount.md)|Získá počet položek ve výčtu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní se obvykle používá ladicí modul k určení uvedenou příslušnou adresu pro vyhodnocovací filtr výrazů.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)
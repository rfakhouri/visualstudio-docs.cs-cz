---
title: IEnumDebugAddresses | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugAddresses
helpviewer_keywords:
- IEnumDebugAddresses interface
ms.assetid: 5f6f6751-e6d8-4c5a-8e81-414b6e5d8cc5
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2373a26da1f6c3b327bea3a6f2402beb7d8bce45
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68196149"
---
# <a name="ienumdebugaddresses"></a>IEnumDebugAddresses
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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

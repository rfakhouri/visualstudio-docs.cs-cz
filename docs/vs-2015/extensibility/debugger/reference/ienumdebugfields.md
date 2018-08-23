---
title: IEnumDebugFields | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEnumDebugFields
helpviewer_keywords:
- IEnumDebugFields interface
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b56a0823ec0c2f02374e46fb8be61277da6adb88
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629222"
---
# <a name="ienumdebugfields"></a>IEnumDebugFields
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IEnumDebugFields](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugfields).  
  
Představuje kolekci objektů implementace tohoto rozhraní [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugFields : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno symbol poskytovatele za účelem poskytnutí sady objektů, které implementují [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní. Všimněte si, že to není standardní výčet COM z důvodu přítomnosti [GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md) metody.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je vrácený [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md) a [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní implementuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|Načte další sadu [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekty z výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|Vynechá zadaný počet položek.|  
|[Resetovat](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|Obnoví výčtu první položka.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|Načte kopii do aktuálního výčtu.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|Získá počet položek ve výčtu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)   
 [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)


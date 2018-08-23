---
title: IEnumDebugCustomAttributes | Dokumentace Microsoftu
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
- IEnumCustomAttributes
helpviewer_keywords:
- IEnumDebugCustomAttributes interface
ms.assetid: 11aa768d-1852-44d6-9de3-17f9bafaded2
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 695fb7c68f76d4cd91c079490436b9aaf38ecd13
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671853"
---
# <a name="ienumdebugcustomattributes"></a>IEnumDebugCustomAttributes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IEnumDebugCustomAttributes](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugcustomattributes).  
  
Vytvoří výčet vlastních atributů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumCustomAttributes : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Poskytovatel symbolů implementuje toto rozhraní pro podporu vlastních atributů (až [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md) rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [Enumcustomattributes –](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md) vrátí toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugCustomAttributes`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md)|Načte zadaný počet vlastních atributů v sekvenci výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugcustomattributes-skip.md)|Vynechá zadaný počet vlastních atributů v sekvenci výčtu.|  
|[Resetovat](../../../extensibility/debugger/reference/ienumdebugcustomattributes-reset.md)|Návrat na začátek sekvence výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugcustomattributes-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcustomattributes-getcount.md)|Získá počet uživatelských atributů, které v enumerátor.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [Enumcustomattributes –](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)   
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)


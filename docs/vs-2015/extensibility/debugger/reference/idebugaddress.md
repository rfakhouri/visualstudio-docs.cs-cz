---
title: IDebugAddress | Dokumentace Microsoftu
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
- IDebugAddress
helpviewer_keywords:
- IDebugAddress interface
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 75a5b1ab9979d7d071282ab4d807d89b5e7abb2b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673627"
---
# <a name="idebugaddress"></a>IDebugAddress
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugAddress](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugaddress).  
  
Toto rozhraní představuje adresu položky. Vrátí obslužnou rutinu symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugAddress : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Poskytovatel symbolů implementuje toto rozhraní představující adresu objektu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Mnoho metod na mnoho rozhraní vrátí toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|Načte [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura popisující objekt a jeho umístění.|  
  
## <a name="remarks"></a>Poznámky  
 Poskytovatel symbolů vrátí toto rozhraní k reprezentaci objektu a jeho umístění v rámci určitého oboru (například funkce, metody nebo třídy). Toto rozhraní je vrácená z a do různých metod poskytovatel symbolů a výraz Chyba při vyhodnocování. Za normálních okolností poskytovatel symbolů je pouze entity, které je potřeba interpretovat obsah tohoto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)


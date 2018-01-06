---
title: IDebugAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAddress
helpviewer_keywords: IDebugAddress interface
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ea03ec205a4bc28f025b8539bc0abf3abc59ceaa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugaddress"></a>IDebugAddress
Toto rozhraní představuje adresu položky. Se vrátí symbol obslužnou rutinou.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugAddress : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Symbol zprostředkovatele implementuje toto rozhraní představující adresu objektu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Mnoho způsobů na mnoho rozhraní vrátí toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getaddress –](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|Načte [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura popisující objektu a jeho umístění.|  
  
## <a name="remarks"></a>Poznámky  
 Zprostředkovatel symbol vrátí toto rozhraní k reprezentaci objektu a jeho umístění v konkrétním oboru (například funkce, metoda nebo třídy). Toto rozhraní je vrácená z a různé metody symbol zprostředkovatele a výraz předaný vyhodnocování. Za normálních okolností zprostředkovatel symbol je pouze entity, která potřebuje interpretovat obsah tohoto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Zprostředkovatel rozhraní symbol](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)
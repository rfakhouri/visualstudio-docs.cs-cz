---
title: IDebugFunctionPosition2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugFunctionPosition2
helpviewer_keywords:
- IDebugFunctionPosition2 interface
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6494f01a10177cc0e3fa0eb1724f64b7301e06aa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionposition2"></a>IDebugFunctionPosition2
Toto rozhraní představuje abstraktní pozici funkci ve zdrojovém dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugFunctionPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představující pozici funkce ve zdrojovém dokumentu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je zadán jako součást [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) sjednocení (konkrétně [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) struktura), je zase součástí [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) Struktura použité při vytváření čekající zarážky.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugFunctionPosition2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|Získá název funkce, která je vzhledem k této pozice.|  
|[Getoffset –](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|Získá posun od začátku funkce.|  
  
## <a name="remarks"></a>Poznámky  
 Pozice reprezentována toto rozhraní je založený na textu, konkrétně [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktury.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)
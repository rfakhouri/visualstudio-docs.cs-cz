---
title: IDebugFunctionPosition2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugFunctionPosition2
helpviewer_keywords:
- IDebugFunctionPosition2 interface
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4811a6f2aa79e2e19524c0ea1e3e687cd7e28220
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68180918"
---
# <a name="idebugfunctionposition2"></a>IDebugFunctionPosition2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní představuje abstraktní pozice funkce ve zdrojovém dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugFunctionPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní k reprezentaci pozice funkce ve zdrojovém dokumentu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je zadaný jako součást [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) sjednocení (konkrétně [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) struktury), který je zase součástí [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) Struktura použité při vytváření čekající zarážkou.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugFunctionPosition2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|Získá název funkce, která je vzhledem k této pozice.|  
|[GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|Získá posun od začátku této funkce.|  
  
## <a name="remarks"></a>Poznámky  
 Pozice reprezentovaný tímto rozhraním je založený na textu, konkrétně [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktury.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)

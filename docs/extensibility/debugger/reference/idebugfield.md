---
title: IDebugField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugField
helpviewer_keywords: IDebugField interface
ms.assetid: adecdd1c-b1b9-4027-92da-74cbe910636f
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 00d3113f0151b9a2ad32259b24cc45dcca8bbccf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfield"></a>IDebugField
Toto rozhraní představuje pole, který je popis symbolu nebo typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugField : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje poskytovatele symbol jako základní třída pro všechna pole.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je základní třídu pro všechna pole. Podle návratová hodnota [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md), toto rozhraní může vrátit více specializované rozhraní pomocí [QueryInterface](/cpp/atl/queryinterface). Kromě toho vrátí mnoho rozhraní `IDebugField` objekty z různých metod.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugField`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)|Získá zobrazitelné informací o symbolu nebo typu.|  
|[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)|Získá druh typu pole.|  
|[GETTYPE –](../../../extensibility/debugger/reference/idebugfield-gettype.md)|Získá typ pole.|  
|[GetContainer](../../../extensibility/debugger/reference/idebugfield-getcontainer.md)|Získá kontejner pole.|  
|[Getaddress –](../../../extensibility/debugger/reference/idebugfield-getaddress.md)|Získá adresu pole.|  
|[Getsize –](../../../extensibility/debugger/reference/idebugfield-getsize.md)|Získá velikost pole, v bajtech.|  
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugfield-getextendedinfo.md)|Získá rozšířené informace o pole.|  
|[Rovná](../../../extensibility/debugger/reference/idebugfield-equal.md)|Porovná dvě pole.|  
|[GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)|Získá nezávislé na typ informací o symbolu nebo typu.|  
  
## <a name="remarks"></a>Poznámky  
 Typ je ekvivalentní pro jazyk C `typedef`.  
  
 V následujícím příkladu jazyk C++ `weather` je typu třídy a `sunny` a `stormy` jsou symboly:  
  
```cpp  
class weather;  
weather sunny;  
weather stormy;  
```  
  
 Jestli pole představuje symbol nebo typ se dá určit pomocí volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) a prozkoumání [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) výsledek. Pokud `FIELD_KIND_TYPE` je nastaven bit, pole je typu a pokud `FIELD_KIND_SYMBOL` je nastaven bit, je symbol.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
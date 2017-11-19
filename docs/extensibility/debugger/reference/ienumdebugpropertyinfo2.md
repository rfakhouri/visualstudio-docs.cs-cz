---
title: IEnumDebugPropertyInfo2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugPropertyInfo2
helpviewer_keywords: IEnumDebugPropertyInfo2
ms.assetid: fdea8262-40b8-473e-88ba-639e4c4648e6
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9e7f261a449e20873183ff59487c1a6b2df6b678
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugpropertyinfo2"></a>IEnumDebugPropertyInfo2
Vytvoří výčet toto rozhraní [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugPropertyInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představující informace o určité vlastnosti.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) k získání tohoto rozhraní představující podřízené objekty konkrétní vlastnosti. Volání [enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) k získání tohoto rozhraní představující vlastnosti konkrétní zásobníku.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IEnumDebugPropertyInfo2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Další](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md)|Načte zadaný počet [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury v posloupnosti výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-skip.md)|Přeskočí zadaný počet [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury v posloupnosti výčtu.|  
|[Resetování](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
|[GetCount –](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)|Získá počet [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Obecně platí je vlastnost hierarchie informace, které mohou zahrnovat název, hodnotu, adresy a typ a také všechny ostatní informace, které jsou vhodné pro přidružené vlastnosti objektu nebo zásobníku rámečku. V tématu [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) další podrobnosti.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [Enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)
---
title: DEBUG_PROPERTY_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_PROPERTY_INFO
helpviewer_keywords:
- DEBUG_PROPERTY_INFO structure
ms.assetid: 5a085d18-62c6-4740-b9e9-3f5db6bfdf7f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4466d74d0e19b898b3c377c67a14f7c39922d915
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="debugpropertyinfo"></a>DEBUG_PROPERTY_INFO
Obsahuje informace o vlastnosti ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct tagDEBUG_PROPERTY_INFO {   
   DEBUGPROP_INFO_FLAGS dwValidFields;  
   BSTR                 bstrFullName;  
   BSTR                 bstrName;  
   BSTR                 bstrType;  
   BSTR                 bstrValue;  
   IDebugProperty2*     pProperty;  
   DBG_ATTRIB_FLAGS     dwAttrib;  
} DEBUG_PROPERTY_INFO;  
```  
  
```csharp  
public struct DEBUG_PROPERTY_INFO {   
   public uint            dwValidFields;  
   public string          bstrFullName;  
   public string          bstrName;  
   public string          bstrType;  
   public string          bstrValue;  
   public IDebugProperty2 pProperty;  
   public ulong           dwAttrib;  
};  
```  
  
## <a name="members"></a>Členové  
 dwValidFields  
 Kombinace příznaků z [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) výčet, který určuje, které jsou vyplněna.  
  
 bstrFullName  
 Úplný název vlastnosti.  
  
 bstrName  
 Název vlastnosti v kontextu.  
  
 bstrType  
 Typ vlastnosti jako řetězec formátovaný.  
  
 bstrValue  
 Hodnota vlastnosti jako řetězec formátovaný.  
  
 pProperty  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt popsaná tuto strukturu.  
  
 dwAttrib  
 Kombinace příznaků z [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) výčet popisující atributy této vlastnosti.  
  
## <a name="remarks"></a>Poznámky  
 Vlastnost je objekt hierarchické povahy, který má název, typ a hodnotu. Například vlastnost popíše lokální proměnné, parametry, sledovat proměnné a výrazy a zaregistruje.  
  
 Tato struktura je předána [GetPropertyInfo –](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) metoda, kde je vyplněna. Tato struktura je také vrácena jako součást Seznam tato struktura z [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) rozhraní, které je zase, vrácena z volání [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) a [ Enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo –](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [Enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)
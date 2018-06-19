---
title: DEBUGPROP_INFO_FLAGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUGPROP_INFO_FLAGS
helpviewer_keywords:
- DBGPROP_INFO_FLAGS enumeration
ms.assetid: 1c7fe777-615e-4929-9ed4-970d9fe0eb81
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1d9ecaab348ca69a792c39a8cb74e998d8f3a6aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31104336"
---
# <a name="debugpropinfoflags"></a>DEBUGPROP_INFO_FLAGS
Určuje, jaké informace načíst o objekt vlastnosti ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DEBUGPROP_INFO_FLAGS {   
   DEBUGPROP_INFO_FULLNAME          = 0x00000001,  
   DEBUGPROP_INFO_NAME              = 0x00000002,  
   DEBUGPROP_INFO_TYPE              = 0x00000004,  
   DEBUGPROP_INFO_VALUE             = 0x00000008,  
   DEBUGPROP_INFO_ATTRIB            = 0x00000010,  
   DEBUGPROP_INFO_PROP              = 0x00000020,  
   DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,  
   DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,  
   DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,  
   DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000  
   DEBUGPROP_INFO_NONE              = 0x00000000,  
   DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |  
                                      DEBUGPROP_INFO_NAME |  
                                      DEBUGPROP_INFO_TYPE |  
                                      DEBUGPROP_INFO_VALUE,  
   DEBUGPROP_INFO_ALL               = 0xffffffff  
};  
typedef DWORD DEBUGPROP_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_DEBUGPROP_INFO_FLAGS {   
   DEBUGPROP_INFO_FULLNAME          = 0x00000001,  
   DEBUGPROP_INFO_NAME              = 0x00000002,  
   DEBUGPROP_INFO_TYPE              = 0x00000004,  
   DEBUGPROP_INFO_VALUE             = 0x00000008,  
   DEBUGPROP_INFO_ATTRIB            = 0x00000010,  
   DEBUGPROP_INFO_PROP              = 0x00000020,  
   DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,  
   DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,  
   DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,  
   DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000  
   DEBUGPROP_INFO_NONE              = 0x00000000,  
   DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |  
                                      DEBUGPROP_INFO_NAME |  
                                      DEBUGPROP_INFO_TYPE |  
                                      DEBUGPROP_INFO_VALUE,  
   DEBUGPROP_INFO_ALL               = 0xffffffff  
};  
```  
  
## <a name="members"></a>Členové  
 DEBUGPROP_INFO_FULLNAME  
 Inicializace nebo pomocí `bstrFullName` pole.  
  
 DEBUGPROP_INFO_NAME  
 Inicializace nebo pomocí `bstrName` pole.  
  
 DEBUGPROP_INFO_TYPE  
 Inicializace nebo pomocí `bstrType` pole.  
  
 DEBUGPROP_INFO_VALUE  
 Inicializace nebo pomocí `bstrValue` pole.  
  
 DEBUGPROP_INFO_ATTRIB  
 Inicializace nebo pomocí `dwAttrib` pole.  
  
 DEBUGPROP_INFO_PROP,  
 Inicializace nebo pomocí `pProperty` pole, která obsahuje [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) rozhraní.  
  
 DEBUGPROP_INFO_VALUE_AUTOEXPAND  
 Určuje, že pole hodnoty musí obsahovat hodnotu rozšířit automaticky, pokud je k dispozici pro tento typ objektu.  
  
 DEBUGPROP_INFO_VALUE_NOFUNCEVAL  
 Zastaralé  
  
 DEBUGPROP_INFO_VALUE_RAW  
 Nevrátí žádné beautified hodnoty nebo členy (tedy Neformátovat hodnoty).  
  
 DEBUGPROP_INFO_VALUE_NO_TOSTRING  
 Nevrátí žádné speciální syntetizovaná hodnoty (například Nevolejte `ToString()` na objekt k vytvoření hodnoty).  
  
 DEBUGPROP_INFO_NONE  
 Určuje, jestli jsou nastavené žádné příznaky.  
  
 DEBUGPROP_INFO_STANDARD  
 Inicializace nebo pomocí `dwAttrib`, `bstrName`, `bstrType`, a `bstrValue` pole.  
  
 DEBUGPROP_INFO_All  
 Určuje masku všechny příznaky.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předávány [GetPropertyInfo –](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md), [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md), a [enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) metody, které určují pole, která se mají inicializovat [ DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury.  
  
 Tyto hodnoty se rovněž používají při `dwFields` členem `DEBUG_PROPERTY_INFO` struktura označuje, která pole struktury je platný a použitá při vrácení strukturu.  
  
 Tyto hodnoty mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo –](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [Enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)
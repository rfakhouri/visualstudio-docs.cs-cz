---
title: FIELD_KIND | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- FIELD_KIND
helpviewer_keywords:
- FIELD_KIND enumeration
ms.assetid: fd522b9c-52e2-42fa-939d-343347d5c3b1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 35a603310986f42141a04f38c7ce26db0d7326fe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="fieldkind"></a>FIELD_KIND
Určuje typ pole, které jsou součástí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_FIELD_KIND {   
   FIELD_KIND_NONE       = 0x00000000,  
  
   // Type of field  
   FIELD_KIND_TYPE       = 0x00000001,  
   FIELD_KIND_SYMBOL     = 0x00000002,  
  
   // Storage type of the field  
   FIELD_TYPE_PRIMITIVE  = 0x00000010,  
   FIELD_TYPE_STRUCT     = 0x00000020,  
   FIELD_TYPE_CLASS      = 0x00000040,  
   FIELD_TYPE_INTERFACE  = 0x00000080,  
   FIELD_TYPE_UNION      = 0x00000100,  
   FIELD_TYPE_ARRAY      = 0x00000200,  
   FIELD_TYPE_METHOD     = 0x00000400,  
   FIELD_TYPE_BLOCK      = 0x00000800,  
   FIELD_TYPE_POINTER    = 0x00001000,  
   FIELD_TYPE_ENUM       = 0x00002000,  
   FIELD_TYPE_LABEL      = 0x00004000,  
   FIELD_TYPE_TYPEDEF    = 0x00008000,  
   FIELD_TYPE_BITFIELD   = 0x00010000,  
   FIELD_TYPE_NAMESPACE  = 0x00020000,  
   FIELD_TYPE_MODULE     = 0x00040000,  
   FIELD_TYPE_DYNAMIC    = 0x00080000,  
   FIELD_TYPE_PROP       = 0x00100000,  
   FIELD_TYPE_INNERCLASS = 0x00200000,  
   FIELD_TYPE_REFERENCE  = 0x00400000,  
   FIELD_TYPE_EXTENDED   = 0x00800000,  
  
   // Specific information about symbols  
   FIELD_SYM_MEMBER      = 0x01000000,  
   FIELD_SYM_LOCAL       = 0x02000000,  
   FIELD_SYM_PARAM       = 0x04000000,  
   FIELD_SYM_THIS        = 0x08000000,  
   FIELD_SYM_GLOBAL      = 0x10000000,  
   FIELD_SYM_PROP_GETTER = 0x20000000,  
   FIELD_SYM_PROP_SETTER = 0x40000000,  
   FIELD_SYM_EXTENDED    = 0x80000000,  
  
   FIELD_KIND_MASK       = 0x0000000f,  
   FIELD_TYPE_MASK       = 0x00fffff0,  
   FIELD_SYM_MASK        = 0xff000000,  
  
   FIELD_KIND_ALL        = 0xffffffff  
};  
typedef DWORD FIELD_KIND;  
```  
  
```csharp  
public enum enum_FIELD_KIND {  
   FIELD_KIND_NONE       = 0x00000000,  
  
   // Type of field  
   FIELD_KIND_TYPE       = 0x00000001,  
   FIELD_KIND_SYMBOL     = 0x00000002,  
  
   // Storage type of the field  
   FIELD_TYPE_PRIMITIVE  = 0x00000010,  
   FIELD_TYPE_STRUCT     = 0x00000020,  
   FIELD_TYPE_CLASS      = 0x00000040,  
   FIELD_TYPE_INTERFACE  = 0x00000080,  
   FIELD_TYPE_UNION      = 0x00000100,  
   FIELD_TYPE_ARRAY      = 0x00000200,  
   FIELD_TYPE_METHOD     = 0x00000400,  
   FIELD_TYPE_BLOCK      = 0x00000800,  
   FIELD_TYPE_POINTER    = 0x00001000,  
   FIELD_TYPE_ENUM       = 0x00002000,  
   FIELD_TYPE_LABEL      = 0x00004000,  
   FIELD_TYPE_TYPEDEF    = 0x00008000,  
   FIELD_TYPE_BITFIELD   = 0x00010000,  
   FIELD_TYPE_NAMESPACE  = 0x00020000,  
   FIELD_TYPE_MODULE     = 0x00040000,  
   FIELD_TYPE_DYNAMIC    = 0x00080000,  
   FIELD_TYPE_PROP       = 0x00100000,  
   FIELD_TYPE_INNERCLASS = 0x00200000,  
   FIELD_TYPE_REFERENCE  = 0x00400000,  
   FIELD_TYPE_EXTENDED   = 0x00800000,  
  
   // Specific information about symbols  
   FIELD_SYM_MEMBER      = 0x01000000,  
   FIELD_SYM_LOCAL       = 0x02000000,  
   FIELD_SYM_PARAM       = 0x04000000,  
   FIELD_SYM_THIS        = 0x08000000,  
   FIELD_SYM_GLOBAL      = 0x10000000,  
   FIELD_SYM_PROP_GETTER = 0x20000000,  
   FIELD_SYM_PROP_SETTER = 0x40000000,  
   FIELD_SYM_EXTENDED    = 0x80000000,  
  
   FIELD_KIND_MASK       = 0x0000000f,  
   FIELD_TYPE_MASK       = 0x00fffff0,  
   FIELD_SYM_MASK        = 0xff000000,  
  
   FIELD_KIND_ALL        = 0xffffffff  
};  
```  
  
## <a name="members"></a>Členové  
 FIELD_KIND_TYPE  
 Označuje, že pole je pouze typ.  
  
 FIELD_KIND_SYMBOL  
 Označuje, že pole je symbol typu, název a další informace.  
  
 FIELD_TYPE_PRIMITIVE  
 Označuje, že je pole typu primitivní datové.  
  
 FIELD_TYPE_STRUCT  
 Označuje, že je pole do struktury.  
  
 FIELD_TYPE_CLASS  
 Označuje, že je pole třídu.  
  
 FIELD_TYPE_INTERFACE  
 Určuje, že je pole rozhraní.  
  
 FIELD_TYPE_UNION  
 Označuje, že je pole spojení.  
  
 FIELD_TYPE_ARRAY  
 Určuje, že je pole pole.  
  
 FIELD_TYPE_METHOD  
 Označuje, že je pole metodu.  
  
 FIELD_TYPE_BLOCK  
 Určuje, že je pole blok.  
  
 FIELD_TYPE_POINTER  
 Určuje, že je pole ukazatel.  
  
 FIELD_TYPE_ENUM  
 Určuje, že je pole Výčtový typ dat.  
  
 FIELD_TYPE_LABEL  
 Označuje, že je pole štítek.  
  
 FIELD_TYPE_TYPEDEF  
 Označuje, že pole je definice typu.  
  
 FIELD_TYPE_BITFIELD  
 Označuje, že je pole bitfield.  
  
 FIELD_TYPE_NAMESPACE  
 Označuje, že je pole obor názvů.  
  
 FIELD_TYPE_MODULE  
 Označuje, že je pole modulu.  
  
 FIELD_TYPE_DYNAMIC  
 Označuje, že je pole dynamické.  
  
 FIELD_TYPE_PROP  
 Označuje, že je pole vlastnosti.  
  
 FIELD_TYPE_INNERCLASS  
 Označuje, že pole je vnitřní třídu.  
  
 FIELD_TYPE_REFERENCE  
 Označuje, že je pole odkazem.  
  
 FIELD_TYPE_EXTENDED  
 Vyhrazeno pro budoucí použití.  
  
 FIELD_SYM_MEMBER  
 Označuje, že je pole členem.  
  
 FIELD_SYM_LOCAL  
 Označuje, že je pole místní.  
  
 FIELD_SYM_PARAMETER  
 Určuje, že je pole parametr.  
  
 FIELD_SYM_THIS  
 Označuje, že je pole "Tento" ukazatel.  
  
 FIELD_SYM_GLOBAL  
 Označuje, že je globální pole.  
  
 FIELD_SYM_PROP_GETTER  
 Označuje, že pole načte vlastnosti.  
  
 FIELD_SYM_PROP_SETTER  
 Označuje, že pole nastaví vlastnosti.  
  
 FIELD_SYM_EXTENDED  
 Vyhrazeno pro budoucí použití.  
  
 FIELD_KIND_MASK  
 Určuje masku pro typy pole.  
  
 FIELD_TYPE_MASK  
 Určuje masku pro typy polí.  
  
 FIELD_SYM_MASK  
 Určuje masku pro informací o symbolu.  
  
## <a name="remarks"></a>Poznámky  
 Vrácená z volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) metoda.  
  
 V závislosti na druhu pole [QueryInterface](/cpp/atl/queryinterface) lze volat [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní pro konkrétnější formuláře rozhraní. Například pokud [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) vrátí `FIELD_TYPE_METHOD`, potom můžete volat `QueryInterface` na I`DebugField` získat [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
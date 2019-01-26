---
title: FIELD_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- FIELD_INFO
helpviewer_keywords:
- FIELD_INFO structure
ms.assetid: bfafef6d-0c83-43d7-a779-1f0d24b166a1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 85d84c88f0b16d1b58e2bd1d85e5ca6b000dc125
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986004"
---
# <a name="fieldinfo"></a>FIELD_INFO
Tato struktura popisuje místní proměnná, parametr nebo jiné pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagFieldInfo {   
   FIELD_INFO_FIELDS dwFields;  
   BSTR              bstrFullName;  
   BSTR              bstrName;  
   BSTR              bstrType;  
   FIELD_MODIFIERS   dwModifiers;  
} FIELD_INFO;  
```  
  
```csharp  
public struct FIELD_INFO {  
   public uint   dwFields;  
   public string bstrFullName;  
   public string bstrName;  
   public string bstrType;  
   public uint   dwModifiers;  
};  
```  
  
## <a name="members"></a>Členové  
 dwFields  
 Kombinace příznaků z [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) výčet, který určuje členy, které jsou vyplněna.  
  
 bstrFullName  
 Celý název pole.  
  
 bstrName  
 Krátký název pole.  
  
 bstrType  
 Typ pole.  
  
 dwModifiers  
 Kombinace příznaků z [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) výčet, který popisuje pole.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předán [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) metody, kde je vyplněna.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md)   
 [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)
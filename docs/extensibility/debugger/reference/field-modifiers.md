---
title: FIELD_MODIFIERS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FIELD_MODIFIERS
helpviewer_keywords: FIELD_MODIFIERS enumeration
ms.assetid: 1e44681c-1f03-41a9-9c04-b79f231b0822
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 98f6e4d3f187261bcf9c0d1ad3959093d864e222
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="fieldmodifiers"></a>FIELD_MODIFIERS
Určuje modifikátory pro typ pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_FIELD_MODIFIERS {   
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
typedef DWORD FIELD_MODIFIERS;  
```  
  
```csharp  
public enum enum_FIELD_MODIFIERS {  
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
```  
  
## <a name="members"></a>Členové  
 FIELD_MOD_ACCESS_TYPE  
 Označuje, že pole není přístupný.  
  
 FIELD_MOD_ACCESS_PUBLIC  
 Určuje, zda má pole veřejný přístup.  
  
 FIELD_MOD_ACCESS_PROTECTED  
 Označuje, že pole je chráněný přístup.  
  
 FIELD_MOD_ACCESS_PRIVATE  
 Určuje, zda má pole soukromý přístup.  
  
 FIELD_MOD_NOMODIFIERS  
 Určuje, zda má pole bez parametrů.  
  
 FIELD_MOD_STATIC  
 Označuje, že je pole statické.  
  
 FIELD_MOD_CONSTANT  
 Označuje, že je pole konstanta.  
  
 FIELD_MOD_TRANSIENT  
 Označuje, že je pole přechodný.  
  
 FIELD_MOD_VOLATILE  
 Označuje, že je pole volatile.  
  
 FIELD_MOD_ABSTRACT  
 Označuje, že pole je abstraktní.  
  
 FIELD_MOD_NATIVE  
 Označuje, že je pole nativní.  
  
 FIELD_MOD_SYNCHRONIZED  
 Označuje, že se synchronizují pole.  
  
 FIELD_MOD_VIRTUAL  
 Označuje, že je pole virtuální.  
  
 FIELD_MOD_INTERFACE  
 Určuje, že je pole rozhraní.  
  
 FIELD_MOD_FINAL  
 Označuje, že je pole poslední.  
  
 FIELD_MOD_SENTINEL  
 Označuje, že je pole sentinel.  
  
 FIELD_MOD_INNERCLASS  
 Označuje, že pole je vnitřní třídu.  
  
 FIELD_TYPE_OPTIONAL  
 Označuje, že pole je volitelné.  
  
 FIELD_MOD_BYREF  
 Označuje, že je pole argument typu odkaz. Toto je speciálně pro argumenty metody.  
  
 FIELD_MOD_HIDDEN  
 Označuje, že pole musí být skrytý nebo uvedené v jiném kontextu; například [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] místní statické hodnoty.  
  
 FIELD_MOD_MARSHALASOBJECT  
 Označuje, že pole představuje objekt se `IUnknown` rozhraní.  
  
 FIELD_MOD_SPECIAL_NAME  
 Určuje, že pole má speciální název, například `.ctor` pro konstruktor ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] pouze).  
  
 FIELD_MOD_HIDEBYSIG  
 Určuje, zda má pole `Overloads` – klíčové slovo na něho použít ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] pouze).  
  
 FIELD_MOD_WRITEONLY  
 Označuje, že pole je jen pro zápis. Tato hodnota není součástí `FIELD_MOD_ALL`, jak používat jenom taková pole jen pro zápis je pro funkce vyhodnocování. Uživatel musí explicitně požádat o `FIELD_MOD_WRITEONLY` pole.  
  
 FIELD_MOD_ACCESS_MASK  
 Určuje masku pro přístup k poli.  
  
 FIELD_MOD_MASK  
 Určuje masku pro Modifikátory polí.  
  
## <a name="remarks"></a>Poznámky  
 Použít pro `dwModifiers` členem [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) struktury.  
  
 Tyto hodnoty jsou také předávány [enumfields –](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md) metoda Chcete-li filtrovat konkrétních polí.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [Enumfields –](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)
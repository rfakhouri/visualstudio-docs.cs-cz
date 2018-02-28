---
title: DEBUGREF_INFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEBUGREF_INFO_FLAGS
helpviewer_keywords:
- DEBUGREF_INFO_FLAGS enumeration
ms.assetid: 1b043327-302a-4f6d-b51d-f94f9d7c7f9d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0ccdf97b532c014636ff19f7416a656ac062f411
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="debugrefinfoflags"></a>DEBUGREF_INFO_FLAGS
Určuje, jaké informace načíst o ladění referenční objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
typedef DWORD DEBUGREF_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
```  
  
## <a name="members"></a>Členové  
 DEBUGREF_INFO_NAME  
 Inicializace nebo pomocí `bstrName` pole ve struktuře.  
  
 DEBUGREF_INFO_TYPE  
 Inicializace nebo pomocí `bstrType` pole ve struktuře.  
  
 DEBUGREF_INFO_VALUE  
 Inicializace nebo pomocí `bstrValue` pole ve struktuře.  
  
 DEBUGREF_INFO_ATTRIB  
 Inicializace nebo pomocí `dwAttrib` pole ve struktuře.  
  
 DEBUGREF_INFO_REFTYPE  
 Inicializace nebo pomocí `dwRefType` pole ve struktuře.  
  
 DEBUGREF_INFO_REF  
 Inicializace nebo pomocí `pReference` pole ve struktuře.  
  
 DEBUGREF_INFO_VALUE_AUTOEXPAND  
 Pole hodnoty musí obsahovat hodnotu rozšířit automaticky, pokud je k dispozici pro tento typ objektu.  
  
 DEBUGREF_INFO_NONE  
 Určuje, jestli jsou nastavené žádné příznaky.  
  
 DEBUGREF_INFO_ALL  
 Určuje masku příznaků.  
  
## <a name="remarks"></a>Poznámky  
 Tyto příznaky jsou předávány [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) a [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) metody označíte, které pole [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktura mají být inicializován.  
  
 Použít pro `dwFields` členem `DEBUG_REFERENCE_INFO` struktura označuje pole, která je platná a použitá při vrácení strukturu.  
  
 Tyto hodnoty mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)   
 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)
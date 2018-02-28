---
title: MODULE_INFO_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MODULE_INFO_FIELDS
helpviewer_keywords:
- MODULE_INFO_FIELDS enumeration
ms.assetid: 8bed85f4-235f-4192-b58f-5fad7a4d7a78
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d96175501d0e75ee1949847c69909c23a3b08582
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="moduleinfofields"></a>MODULE_INFO_FIELDS
Určuje příznaky pro ladicí informace o modulu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_MODULE_INFO_FIELDS {   
   MIF_NONE              = 0x0000,  
   MIF_NAME              = 0x0001,  
   MIF_URL               = 0x0002,  
   MIF_VERSION           = 0x0004,  
   MIF_DEBUGMESSAGE      = 0x0008,  
   MIF_LOADADDRESS       = 0x0010,  
   MIF_PREFFEREDADDRESS  = 0x0020,  
   MIF_SIZE              = 0x0040,  
   MIF_LOADORDER         = 0x0080,  
   MIF_TIMESTAMP         = 0x0100,  
   MIF_URLSYMBOLLOCATION = 0x0200,  
   MIF_FLAGS             = 0x0400,  
   MIF_ALLFIELDS         = 0x07ff  
};  
typedef DWORD MODULE_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_MODULE_INFO_FIELDS {   
   MIF_NONE              = 0x0000,  
   MIF_NAME              = 0x0001,  
   MIF_URL               = 0x0002,  
   MIF_VERSION           = 0x0004,  
   MIF_DEBUGMESSAGE      = 0x0008,  
   MIF_LOADADDRESS       = 0x0010,  
   MIF_PREFFEREDADDRESS  = 0x0020,  
   MIF_SIZE              = 0x0040,  
   MIF_LOADORDER         = 0x0080,  
   MIF_TIMESTAMP         = 0x0100,  
   MIF_URLSYMBOLLOCATION = 0x0200,  
   MIF_FLAGS             = 0x0400,  
   MIF_ALLFIELDS         = 0x07ff  
};  
```  
  
## <a name="members"></a>Členové  
 MIF_NONE  
 Inicializace nebo použití žádné pole ve struktuře.  
  
 MIF_NAME  
 Inicializace nebo použití `m_bstrName` pole [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) struktura.  
  
 MIF_URL  
 Inicializace nebo použití `m_bstrUrl` pole `MODULE_INFO` struktura.  
  
 MIF_VERSION  
 Inicializace nebo použití `m_bstrVersion` pole `MODULE_INFO` struktura.  
  
 MIF_DEBUGMESSAGE  
 Inicializace nebo použití `m_bstrDebugMessage` pole `MODULE_INFO` struktura.  
  
 MIF_LOADADDRESS  
 Inicializace nebo použití `m_addrLoadAddress` pole `MODULE_INFO` struktura.  
  
 MIF_PREFFEREDADDRESS  
 Inicializace nebo použití `m_addrPreferredLoadAddress` pole `MODULE_INFO` struktura.  
  
 MIF_SIZE  
 Inicializace nebo použití `m_dwSize` pole `MODULE_INFO` struktura.  
  
 MIF_LOADORDER  
 Inicializace nebo použití `m_dwLoadOrder` pole `MODULE_INFO` struktura.  
  
 MIF_TIMESTAMP  
 Inicializace nebo použití `m_TimeStamp` pole `MODULE_INFO` struktura.  
  
 MIF_URLSYMBOLLOCATION  
 Inicializace nebo použití `m_bstrUrlSymbolLocation` pole `MODULE_INFO` struktura.  
  
 MIF_FLAGS  
 Inicializace nebo použití `m_dwModuleFlags` pole `MODULE_INFO` struktura.  
  
 MIF_ALLFIELDS  
 Inicializace nebo použití, všechna pole v `MODULE_INFO` struktura.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předávány jako argument pro [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) metoda označíte, které pole [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) struktura mají být inicializován.  
  
 Tyto hodnoty se také používají v `MODULE_INFO` struktura označuje pole, která je platná a použitá.  
  
 Tyto příznaky mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)
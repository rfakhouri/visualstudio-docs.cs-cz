---
title: MODULE_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MODULE_INFO
helpviewer_keywords:
- MODULE_INFO structure
ms.assetid: f2e06180-1ab3-4eb5-a428-7994cceb61b6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6e28756873339d504efba417d9e2fe2cc00000b4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="moduleinfo"></a>MODULE_INFO
Popisuje konkrétního modulu (knihovny DLL, EXE nebo sestavení).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct tagMODULE_INFO {   
   MODULE_INFO_FIELDS dwValidFields;  
   BSTR               m_bstrName;  
   BSTR               m_bstrUrl;  
   BSTR               m_bstrVersion;  
   BSTR               m_bstrDebugMessage;  
   UINT64             m_addrLoadAddress;  
   UINT64             m_addrPreferredLoadAddress;  
   DWORD              m_dwSize;  
   DWORD              m_dwLoadOrder;  
   FILETIME           m_TimeStamp;  
   BSTR               m_bstrUrlSymbolLocation;  
   MODULE_FLAGS       m_dwModuleFlags;  
} MODULE_INFO;  
```  
  
```csharp  
public struct MODULE_INFO {   
   public uint     dwValidFields;  
   public string   m_bstrName;  
   public string   m_bstrUrl;  
   public string   m_bstrVersion;  
   public string   m_bstrDebugMessage;  
   public ulong    m_addrLoadAddress;  
   public ulong    m_addrPreferredLoadAddress;  
   public uint     m_dwSize;  
   public uint     m_dwLoadOrder;  
   public FILETIME m_TimeStamp;  
   public string   m_bstrUrlSymbolLocation;  
   public uint     m_dwModuleFlags;  
};  
```  
  
## <a name="members"></a>Členové  
 dwValidFields  
 Kombinace příznaků z [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) výčet, který určuje pole, která jsou vyplněna.  
  
 m_bstrName  
 Název modulu.  
  
 m_bstrUrl  
 Adresa URL modulu.  
  
 m_bstrVersion  
 Verze modulu.  
  
 m_bstrDebugMessage  
 Volitelné zprávu o modulu, například "symboly nelze načíst."  
  
 m_addrLoadAddress  
 Adresa zatížení modulu.  
  
 m_addrPreferredLoadAddress  
 Adresa upřednostňovaného zatížení modul.  
  
 m_dwSize  
 Velikost modulu.  
  
 m_dwLoadOrder  
 Pořadí načítání modulu.  
  
 m_TimeStamp  
 Čas poslední úpravy souboru symbol.  
  
 m_bstrUrlSymbolLocation  
 Umístění souboru se symboly (například ".\\") zadaný v modulu. Použít jako výchozí umístění k vyhledání symboly pro modul.  
  
 m_dwModuleFlags  
 Kombinace příznaků z [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md) výčet, který popisuje modul.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předána [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) metoda, kde je vyplněna.  
  
 Tato struktura odpovídá každý modul uvedené v **moduly** okno.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)   
 [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)
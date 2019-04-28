---
title: MODULE_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MODULE_INFO
helpviewer_keywords:
- MODULE_INFO structure
ms.assetid: f2e06180-1ab3-4eb5-a428-7994cceb61b6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0e3a11e368b6260d00f3f6ed0b19d94aa26bd31a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62865463"
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
 dwValidFields A kombinace příznaků z [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) výčet, který určuje, která pole jsou vyplněna.

 m_bstrName název modulu.

 Adresa URL modulu m_bstrUrl.

 m_bstrVersion verze modulu.

 m_bstrDebugMessage volitelnou zprávu o modulu, třeba "symboly nelze načíst."

 m_addrLoadAddress modulu načtení adresy.

 m_addrPreferredLoadAddress adresu upřednostňované načtení modulu.

 m_dwSize velikost modulu.

 m_dwLoadOrder pořadí načtení modulu.

 m_TimeStamp čas poslední změny souboru symbolů.

 m_bstrUrlSymbolLocation umístění souborů symbolů (například ".\\") zadaný v modulu. Najít symboly pro modul se používá jako výchozí umístění.

 m_dwModuleFlags A kombinace příznaků z [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md) výčet, který popisuje modulu.

## <a name="remarks"></a>Poznámky
 Tato struktura je předán [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) metody, kde je vyplněna.

 Tato struktura odpovídá jednotlivých modulů uvedených v **moduly** okna.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)
- [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)
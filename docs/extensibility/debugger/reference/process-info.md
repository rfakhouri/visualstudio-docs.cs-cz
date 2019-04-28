---
title: PROCESS_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROCESS_INFO
helpviewer_keywords:
- PROCESS_INFO structure
ms.assetid: 260c33cc-a05e-4645-84b6-536d0b3b0537
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a18d9a158e69fd18319f187274a2db7d00e24546
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913475"
---
# <a name="processinfo"></a>PROCESS_INFO
Obsahuje informace o procesu.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct tagPROCESS_INFO { 
   PROCESS_INFO_FIELDS Fields;
   BSTR                bstrFileName;
   BSTR                bstrBaseName;
   BSTR                bstrTitle;
   AD_PROCESS_ID       ProcessId;
   DWORD               dwSessionId;
   BSTR                bstrAttachedSessionName;
   FILETIME            CreationTime;
   PROCESS_INFO_FLAGS  Flags;
} PROCESS_INFO;
```

```csharp
public struct PROCESS_INFO { 
   public uint          Fields;
   public string        bstrFileName;
   public string        bstrBaseName;
   public string        bstrTitle;
   public AD_PROCESS_ID ProcessId;
   public uint          dwSessionId;
   public string        bstrAttachedSessionName;
   public FILETIME      CreationTime;
   public uint          Flags;
};
```

## <a name="members"></a>Členové
 Kombinace příznaků z pole [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) výčet určující, která pole jsou vyplněna.

 bstrFileName úplný název cesty procesu. Ekvivalentní volání [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) metody s parametrem `GN_FILENAME`.

 bstrBaseName název souboru a přípony procesu. Ekvivalentní volání `IDebugProcess2::Getname` metody s parametrem `GN_BASENAME`.

 bstrTitle název procesu, pokud existuje. Ekvivalentní volání `IDebugProcess2::Getname` metody s parametrem `GN_TITLE`.

 ProcessId [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) strukturu, která identifikuje procesu. Ekvivalentní volání [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md) metody.

 dwSessionId identifikátor, na kterém běží tento proces v relaci ladění.

 bstrAttachedSessionName název připojené relaci. Ekvivalentní volání [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md) metody.

 CreationTime čas vytvoření procesu.

 Kombinace příznaků z příznaků [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md) výčet, který určit vlastnosti procesu.

## <a name="remarks"></a>Poznámky
 Tato struktura je předán [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) metody, kde je vyplněna.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)
- [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md)
- [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)
- [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)
- [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)
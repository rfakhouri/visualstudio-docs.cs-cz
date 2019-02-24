---
title: PROVIDER_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROVIDER_FLAGS
helpviewer_keywords:
- PROVIDER_FLAGS enumeration
ms.assetid: 8cbd2312-ed2f-4477-b192-c3f25c6098c3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 803d9569c611e3c4cd70f2c82ecd525716d8ddb3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687494"
---
# <a name="providerflags"></a>PROVIDER_FLAGS
Určuje požadované vlastnosti ho získat od zprostředkovatele programu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_PROVIDER_FLAGS {
   PFLAG_NONE                    = 0x00,
   PFLAG_REMOTE_PORT             = 0x01,
   PFLAG_DEBUGGEE                = 0x02,
   PFLAG_ATTACHED_TO_DEBUGGEE    = 0x04,
   PFLAG_REASON_WATCH            = 0x08,
   PFLAG_GET_PROGRAM_NODES       = 0x10,
   PFLAG_GET_IS_DEBUGGER_PRESENT = 0x20
};
typedef DWORD PROVIDER_FLAGS;
```

```csharp
public enum enum_PROVIDER_FLAGS {
   PFLAG_NONE                    = 0x00,
   PFLAG_REMOTE_PORT             = 0x01,
   PFLAG_DEBUGGEE                = 0x02,
   PFLAG_ATTACHED_TO_DEBUGGEE    = 0x04,
   PFLAG_REASON_WATCH            = 0x08,
   PFLAG_GET_PROGRAM_NODES       = 0x10,
   PFLAG_GET_IS_DEBUGGER_PRESENT = 0x20
};
```

## <a name="members"></a>Členové
 Zadané příznaky PFLAG_NONE č.

 Volající PFLAG_REMOTE_PORT vyžaduje seznam programů na jiném počítači než [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)].

 Proces je momentálně laděna touto instancí PFLAG_DEBUGGEE [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)].

 PFLAG_ATTACH_TODEBUGGEE [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] je připojen k laděnému programu, ale se nespustila.

 PFLAG_REASON_WATCH [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] je sledování událostí.

 Volající PFLAG_GET_PROGRAM_NODES vyžaduje `ProgramNodes` pole [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md) struktury.

 Volající PFLAG_GET_IS_DEBUGGER_PRESENT vyžaduje `fIsTheDebuggerPresent` pole `PROVIDER_PROCESS_DATA` struktury.

## <a name="remarks"></a>Poznámky
 Tyto příznaky jsou předány do následujících metod:

- [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)

- [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)

- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)

  Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)
- [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)
- [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)
- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)
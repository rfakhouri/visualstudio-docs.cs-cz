---
title: PROCESS_INFO_FIELDS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROCESS_INFO_FIELDS
helpviewer_keywords:
- PROCESS_INFO_FIELDS enumeration
ms.assetid: 0d9cc345-3d3a-44d8-ae15-a67acb97a828
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 835509048e888e13b91c53d9e35bd03d7aebdfed
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56701261"
---
# <a name="processinfofields"></a>PROCESS_INFO_FIELDS
Zadaný druh informací k načtení procesu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_PROCESS_INFO_FIELDS { 
   PIF_FILE_NAME             = 0x00000001,
   PIF_BASE_NAME             = 0x00000002,
   PIF_TITLE                 = 0x00000004,
   PIF_PROCESS_ID            = 0x00000008,
   PIF_SESSION_ID            = 0x00000010,
   PIF_ATTACHED_SESSION_NAME = 0x00000020,
   PIF_CREATION_TIME         = 0x00000040,
   PIF_FLAGS                 = 0x00000080,
   PIF_ALL                   = 0x000000ff
};
typedef DWORD PROCESS_INFO_FIELDS;
```

```csharp
public enum enum_PROCESS_INFO_FIELDS { 
   PIF_FILE_NAME             = 0x00000001,
   PIF_BASE_NAME             = 0x00000002,
   PIF_TITLE                 = 0x00000004,
   PIF_PROCESS_ID            = 0x00000008,
   PIF_SESSION_ID            = 0x00000010,
   PIF_ATTACHED_SESSION_NAME = 0x00000020,
   PIF_CREATION_TIME         = 0x00000040,
   PIF_FLAGS                 = 0x00000080,
   PIF_ALL                   = 0x000000ff
};
```

## <a name="members"></a>Členové
 PIF_FILE_NAME inicializace/použít `bstrFileName` pole [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury.

 PIF_BASE_NAME inicializace/použít `bstrBaseName` pole `PROCESS_INFO` struktury.

 PIF_TITLE inicializace/použít `bstrTitle` pole `PROCESS_INFO` struktury.

 PIF_PROCESS_ID inicializace/použít `ProcessId` pole `PROCESS_INFO` struktury.

 PIF_SESSION_ID inicializace/použít `dwSessionId` pole `PROCESS_INFO` struktury.

 PIF_ATTACHED_SESSION_NAME inicializace/použít `bstrAttachedSessionName` pole `PROCESS_INFO` struktury.

 PIF_CREATION_TIME inicializace/použít `CreationTime` pole `PROCESS_INFO` struktury.

 PIF_FLAGS inicializace/použít `Flags` pole `PROCESS_INFO` struktury.

 PIF_ALL vyplní všechna pole.

## <a name="remarks"></a>Poznámky
 Předány [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) indikace polí s [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury mají být inicializovány.

 Používá se také v `Fields` pole `PROCESS_INFO` struktury k označení pole, která se používá a je platný.

 Tyto příznaky lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)
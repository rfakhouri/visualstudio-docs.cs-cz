---
title: PROCESS_INFO_FIELDS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROCESS_INFO_FIELDS
helpviewer_keywords:
- PROCESS_INFO_FIELDS enumeration
ms.assetid: 0d9cc345-3d3a-44d8-ae15-a67acb97a828
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fe9a1854fe5583d001e1dc156bfad5833fd1c08f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66309460"
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

## <a name="fields"></a>Pole
 `PIF_FILE_NAME`\
 Inicializace/použít `bstrFileName` pole [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury.

 `PIF_BASE_NAME`\
 Inicializace/použít `bstrBaseName` pole `PROCESS_INFO` struktury.

 `PIF_TITLE`\
 Inicializace/použít `bstrTitle` pole `PROCESS_INFO` struktury.

 `PIF_PROCESS_ID`\
 Inicializace/použít `ProcessId` pole `PROCESS_INFO` struktury.

 `PIF_SESSION_ID`\
 Inicializace/použít `dwSessionId` pole `PROCESS_INFO` struktury.

 `PIF_ATTACHED_SESSION_NAME`\
 Inicializace/použít `bstrAttachedSessionName` pole `PROCESS_INFO` struktury.

 `PIF_CREATION_TIME`\
 Inicializace/použít `CreationTime` pole `PROCESS_INFO` struktury.

 `PIF_FLAGS`\
 Inicializace/použít `Flags` pole `PROCESS_INFO` struktury.

 `PIF_ALL`\
 Vyplní všechna pole.

## <a name="remarks"></a>Poznámky
 Předány [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) indikace polí s [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury mají být inicializovány.

 Používá se také v `Fields` pole `PROCESS_INFO` struktury k označení pole, která se používá a je platný.

 Tyto příznaky lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)
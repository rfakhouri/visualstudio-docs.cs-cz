---
title: AD_PROCESS_ID | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- AD_PROCESS_ID
helpviewer_keywords:
- AD_PROCESS_ID union
ms.assetid: 4cb40d12-2e92-4f09-83f4-689928bd65b3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e03b51081b082c1180091e823eead47a21a7b3d2
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315427"
---
# <a name="adprocessid"></a>AD_PROCESS_ID
Určuje ID procesu, který může být ID systému nebo identifikátor GUID.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _AD_PROCESS_ID {
    AD_PROCESS_ID_TYPE ProcessIdType;
    union {
        DWORD dwProcessId; 
        GUID  guidProcessId; 
        DWORD dwUnused; 
    } ProcessId;
} AD_PROCESS_ID;
```

```csharp
public struct AD_PROCESS_ID {
    AD_PROCESS_ID_TYPE ProcessIdType;
    DWORD              dwProcessId; 
    GUID               guidProcessId; 
    DWORD              dwUnused; 
};
```

## <a name="members"></a>Členové
`ProcessIdType`  
Hodnota z [AD_PROCESS_ID_TYPE](../../../extensibility/debugger/reference/ad-process-id-type.md) výčet určující, jak interpretovat `ProcessId` sjednocení (nebo pro spravovaný kód, který člen struktury pro přístup k).

dwProcessId  
ID procesu jako hodnotu ze systému.

guidProcessId  
ID procesu jako identifikátor GUID.

dwUnused  
Odsazení.

## <a name="remarks"></a>Poznámky
Tato struktura je předán do následujících metod:

- [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)

- [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)

- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)

- [GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)

A je vrácena z následujících metod:

- [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)

- [GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)  
[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)  
[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)  
[AD_PROCESS_ID_TYPE](../../../extensibility/debugger/reference/ad-process-id-type.md)  
[GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
[GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)  
[GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)  
[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)  
[GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)

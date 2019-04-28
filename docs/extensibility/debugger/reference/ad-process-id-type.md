---
title: AD_PROCESS_ID_TYPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AD_PROCESS_ID_TYPE
helpviewer_keywords:
- AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 405d11b0c685017d59251ba83126a73fe1a96db2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925270"
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
Určuje, jak interpretovat ID procesu v [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktury.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_AD_PROCESS_ID {
    AD_PROCESS_ID_SYSTEM = 0,
    AD_PROCESS_ID_GUID   = 1
};
typedef DWORD AD_PROCESS_ID_TYPE;
```

```csharp
public enum enum_AD_PROCESS_ID {
    AD_PROCESS_ID_SYSTEM = 0,
    AD_PROCESS_ID_GUID   = 1
};
```

## <a name="members"></a>Členové
ID procesu AD_PROCESS_ID_SYSTEM je identifikátor systému. Použití `ProcessId.dwProcessId` pole [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktury.

ID procesu AD_PROCESS_ID_GUID je identifikátor GUID. Použití `ProcessId.guidProcessId` pole `AD_PROCESS_ID` struktury.

## <a name="remarks"></a>Poznámky
Používá pro `ProcessIdType` člena [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) strukturu, která určuje typ ID procesu, který je obsažen ve struktuře. Určuje, jak interpretovat `ProcessId` sjednocení ve struktuře.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)

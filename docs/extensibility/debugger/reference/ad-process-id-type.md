---
title: AD_PROCESS_ID_TYPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
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
ms.openlocfilehash: 2c600dd1fcf22ac7e32e91a38c98d6f524a9ba79
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315648"
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
[Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)

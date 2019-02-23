---
title: m_stateflags – pole | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- m_stateFlags field, Task class [.NET Framework debug engines]
ms.assetid: 82b20efc-08f2-4cd2-91f6-4e01e3da906b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b6766fa98d6141005ed88d623ef8608035593a2a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56704589"
---
# <a name="mstateflags-field"></a>m_stateflags – pole
Ukládá informace o aktuálním stavu <xref:System.Threading.Tasks.Task> objektu.

 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **Sestavení:** mscorlib (v *mscorlib.dll*)

 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.

## <a name="syntax"></a>Syntaxe

```csharp
.field assembly int32 modreq(System.Runtime.CompilerServices.IsVolatile) m_stateFlags
```

## <a name="remarks"></a>Poznámky
 Obvykle se používá <xref:System.Threading.Tasks.Task.Status%2A?displayProperty=fullName> vlastnosti pro přístup k této hodnotě.

 Tento člen může být libovolnou kombinací těchto hodnot:

-   [TASK_STATE_EXECUTED](../../extensibility/debugger/task-state-executed-field.md)

-   [TASK_STATE_FAULTED](../../extensibility/debugger/task-state-faulted-field.md)

-   [TASK_STATE_CANCELED](../../extensibility/debugger/task-state-canceled-field.md)

-   [TASK_STATE_WAITING_ON_CHILDREN](../../extensibility/debugger/task-state-waiting-on-children-field.md)

-   [TASK_STATE_RAN_TO_COMPLETION](../../extensibility/debugger/task-state-ran-to-completion-field.md)

## <a name="see-also"></a>Viz také:
- [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)
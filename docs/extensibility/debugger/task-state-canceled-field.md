---
title: Task_state_canceled – pole | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TASK_STATE_CANCELED field, Task class [.NET Framework debug engines]
ms.assetid: f4f5a96a-8230-493d-9696-8d2716bda261
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b022daee6e71cd0728c2c161eb3e75a865304d04
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62912723"
---
# <a name="taskstatecanceled-field"></a>Task_state_canceled – pole
Úloha byla zrušena před dosáhla do stavu spuštěno nebo potvrzené jeho zrušení a dokončen bez výjimky.

 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **Sestavení:** mscorlib (v knihovně mscorlib.dll)

 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.

## <a name="syntax"></a>Syntaxe

```csharp
.field static assembly literal int32 TASK_STATE_CANCELED = int32(0x00800000)
```

## <a name="remarks"></a>Poznámky
 Pokud [m_stateflags –](../../extensibility/debugger/m-stateflags-field.md) pole obsahuje tuto hodnotu <xref:System.Threading.Tasks.Task.Status%2A> vrátí vlastnost <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>.

## <a name="see-also"></a>Viz také:
- [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)
---
title: Task_state_executed – pole | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TASK_STATE_EXECUTED field, Task class [.NET Framework debug engines]
ms.assetid: 75b8f9d0-b908-40d0-b109-70feaed2ab0c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7a822a47948df80c84ed6845590d5ec2a8c91ec6
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684907"
---
# <a name="taskstateexecuted-field"></a>Task_state_executed – pole
Úloha běží, ale zatím není dokončený.

 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **Sestavení:** mscorlib (v knihovně mscorlib.dll)

 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.

## <a name="syntax"></a>Syntaxe

```csharp
.field static assembly literal int32 TASK_STATE_EXECUTED = int32(0x00020000)
```

## <a name="remarks"></a>Poznámky
 Pokud [m_stateflags –](../../extensibility/debugger/m-stateflags-field.md) pole obsahuje tuto hodnotu <xref:System.Threading.Tasks.Task.Status%2A> vrátí vlastnost <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>.

## <a name="see-also"></a>Viz také:
- [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)
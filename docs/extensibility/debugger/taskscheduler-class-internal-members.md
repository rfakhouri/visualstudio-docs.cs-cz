---
title: Třída TaskScheduler – vnitřní členy | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TaskScheduler class [.NET Framework debug engines]
- debug engines, TaskScheduler class [.NET Framework]
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 865e12819a5e7325886c0f7f5d8425a6b3d2e393
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66331335"
---
# <a name="taskscheduler-class---internal-members"></a>Třída TaskScheduler – vnitřní členy
Tento článek popisuje interní členy <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> třída, která vám pomůže implementovat vlastní ladicího programu. Obecné informace o této třídy, najdete v článku <xref:System.Threading.Tasks.TaskScheduler> článku.

 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **Sestavení:** mscorlib (v *mscorlib.dll*)

 Protože tyto vnitřní členy nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.

## <a name="syntax"></a>Syntaxe

```csharp
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler
       extends System.Object
```

## <a name="members"></a>Členové

### <a name="methods"></a>Metody

|Name|Popis|
|----------|-----------------|
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|Načte pole všech naplánovaných úloh.|
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|Pole všech <xref:System.Threading.Tasks.TaskScheduler> objekty, které jsou momentálně aktivní.|

## <a name="remarks"></a>Poznámky

## <a name="see-also"></a>Viz také:
- <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>
- [Interní informace o paralelním rozšíření pro rozhraní .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
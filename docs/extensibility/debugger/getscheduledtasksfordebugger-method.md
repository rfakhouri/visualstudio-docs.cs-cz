---
title: Getscheduledtasksfordebugger – metoda | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 221a1b49bd3083e0d2dd0248cdf182d699423057
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62889928"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger – metoda
Načte pole všech naplánovaných úloh.

 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **Sestavení:** mscorlib (v *mscorlib.dll*)

 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.

## <a name="syntax"></a>Syntaxe

```csharp
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed
```

## <a name="return-value"></a>Návratová hodnota
 Pole všech naplánovaných úloh. Každý úkol je spuštěn nebo byl dokončen.

## <a name="remarks"></a>Poznámky
 Tato metoda není bezpečná a byste neměli používat souběžně s jinými instancemi <xref:System.Threading.Tasks.TaskScheduler>. Tuto metodu lze volejte z ladicího programu pouze v případě, že ladicí program byla pozastavena všechna ostatní vlákna.

## <a name="see-also"></a>Viz také:
- [Třída TaskScheduler](../../extensibility/debugger/taskscheduler-class-internal-members.md)
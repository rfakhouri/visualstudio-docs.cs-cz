---
title: Paralelní interní informace o rozšíření pro rozhraní .NET Framework | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ad538269f7c6cd11c6a3b93d60c283c5f63558ef
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55028635"
---
# <a name="parallel-extension-internals-for-the-net-framework"></a>Interní informace o paralelním rozšíření pro rozhraní .NET Framework
Tato část popisuje vnitřní typy, metody a pole třídy, které vám pomohou implementovat vlastní ladicího programu pro paralelní rozšíření pro rozhraní .NET Framework.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)  
 Popisuje vnitřní datové členy <xref:System.Threading.Tasks.Task?displayProperty=fullName> třídy.  
  
 [Třída TaskScheduler](../../extensibility/debugger/taskscheduler-class-internal-members.md)  
 Popisuje vnitřní datové členy <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> třídy.  
  
 [Třída ContingentProperties](../../extensibility/debugger/contingentproperties-class-internal-members.md)  
 Popisuje vnitřní datové členy `System.Threading.Tasks.ContingentProperties` třídy.  
  
 [Struktura AsyncTaskMethodBuilder](../../extensibility/debugger/asynctaskmethodbuilder-structure-internal-members.md)  
 Popisuje vnitřní členy <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> struktury.  
  
 [AsyncTaskMethodBuilder\<TResult > struktury](../../extensibility/debugger/asynctaskmethodbuilder-tresult-structure-internal-members.md)  
 Popisuje vnitřní členy <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> struktury.  
  
 [Struktura asyncvoidmethodbuilder Structure](../../extensibility/debugger/asyncvoidmethodbuilder-structure-internal-members.md)  
 Popisuje vnitřní členy <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder> struktury.  
  
## <a name="see-also"></a>Viz také:  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Rozšiřitelnost ladicího programu Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)   
 [Paralelní programování](/dotnet/standard/parallel-programming/index)
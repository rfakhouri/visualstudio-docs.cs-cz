---
title: Paralelní interní informace o rozšíření pro rozhraní .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4cc64270cabb3e30ee3c13a1617222349e7b3677
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="parallel-extension-internals-for-the-net-framework"></a>Interní informace o paralelní rozšíření pro rozhraní .NET Framework
Tato část popisuje interní typy metod a pole třídy, které vám pomohou implementovat vlastní ladicí program pro paralelní rozšíření rozhraní .NET Framework.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Task – třída](../../extensibility/debugger/task-class-internal-members.md)  
 Popisuje interních datových členů <xref:System.Threading.Tasks.Task?displayProperty=fullName> třídy.  
  
 [TaskScheduler – třída](../../extensibility/debugger/taskscheduler-class-internal-members.md)  
 Popisuje interních datových členů <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> třídy.  
  
 [ContingentProperties – třída](../../extensibility/debugger/contingentproperties-class-internal-members.md)  
 Popisuje interních datových členů `System.Threading.Tasks.ContingentProperties` třídy.  
  
 [Struktura AsyncTaskMethodBuilder](../../extensibility/debugger/asynctaskmethodbuilder-structure-internal-members.md)  
 Popisuje interní členů <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> struktura.  
  
 [AsyncTaskMethodBuilder\<TResult> Structure](../../extensibility/debugger/asynctaskmethodbuilder-tresult-structure-internal-members.md)  
 Popisuje interní členů <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> struktura.  
  
 [AsyncVoidMethodBuilder Structure](../../extensibility/debugger/asyncvoidmethodbuilder-structure-internal-members.md)  
 Popisuje interní členů <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder> struktura.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Rozšiřitelnost ladicího programu sady Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)   
 [Paralelní programování](/dotnet/standard/parallel-programming/index)
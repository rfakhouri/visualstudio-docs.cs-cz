---
title: Paralelní interní informace o rozšíření pro rozhraní .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4936efe50023ed1e193d0c2ec0d9c3423ac5cc64
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100608"
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
  
 [AsyncTaskMethodBuilder\<TResult > Struktura](../../extensibility/debugger/asynctaskmethodbuilder-tresult-structure-internal-members.md)  
 Popisuje interní členů <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> struktura.  
  
 [Struktura AsyncVoidMethodBuilder](../../extensibility/debugger/asyncvoidmethodbuilder-structure-internal-members.md)  
 Popisuje interní členů <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder> struktura.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Rozšiřitelnost ladicího programu sady Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)   
 [Paralelní programování](/dotnet/standard/parallel-programming/index)
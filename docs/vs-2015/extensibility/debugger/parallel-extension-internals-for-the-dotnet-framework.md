---
title: Paralelní interní informace o rozšíření pro rozhraní .NET Framework | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 42c472190469e7d008fa8c525f50eabfaf37053f
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65680930"
---
# <a name="parallel-extension-internals-for-the-net-framework"></a>Interní informace o paralelním rozšíření pro rozhraní .NET Framework
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tato část popisuje vnitřní typy, metody a pole třídy, které vám pomohou implementovat vlastní ladicího programu pro paralelní rozšíření pro rozhraní .NET Framework.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Task – třída](../../extensibility/debugger/task-class-internal-members.md)  
 Popisuje vnitřní datové členy <xref:System.Threading.Tasks.Task?displayProperty=fullName> třídy.  
  
 [TaskScheduler – třída](../../extensibility/debugger/taskscheduler-class-internal-members.md)  
 Popisuje vnitřní datové členy <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> třídy.  
  
 [ContingentProperties – třída](../../extensibility/debugger/contingentproperties-class-internal-members.md)  
 Popisuje vnitřní datové členy `System.Threading.Tasks.ContingentProperties` třídy.  
  
 [AsyncTaskMethodBuilder – struktura](../../extensibility/debugger/asynctaskmethodbuilder-structure-internal-members.md)  
 Popisuje vnitřní členy <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> struktury.  
  
 [Struktura AsyncTaskMethodBuilder\<TResult>](../../extensibility/debugger/asynctaskmethodbuilder-tresult-structure-internal-members.md)  
 Popisuje vnitřní členy <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> struktury.  
  
 [AsyncVoidMethodBuilder – struktura](../../extensibility/debugger/asyncvoidmethodbuilder-structure-internal-members.md)  
 Popisuje vnitřní členy <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder> struktury.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Rozšiřitelnost ladicího programu sady Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)   
 [Paralelní programování](https://msdn.microsoft.com/library/4d83c690-ad2d-489e-a2e0-b85b898a672d)

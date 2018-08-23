---
title: Paralelní interní informace o rozšíření pro rozhraní .NET Framework | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 16ce4309cc8951d068b3d048e6bfac9ae863cd89
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668358"
---
# <a name="parallel-extension-internals-for-the-net-framework"></a>Interní informace o paralelním rozšíření pro rozhraní .NET Framework
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [paralelní vnitřní fungování rozšíření pro rozhraní .NET Framework](https://docs.microsoft.com/visualstudio/extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework).  
  
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
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Rozšiřitelnost ladicího programu sady Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)   
 [Paralelní programování](http://msdn.microsoft.com/library/4d83c690-ad2d-489e-a2e0-b85b898a672d)


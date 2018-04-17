---
title: AsyncTaskMethodBuilder&lt;TResult&gt; strukturu – vnitřní členy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- AsyncTaskMethodBuilder<TResult> structure [.NET Framework debug engines]
- debug engines, AsyncTaskMethodBuilder<TResult> structure [.NET Framework]
ms.assetid: 17ebc340-8170-4aff-bf54-dc4548c83632
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4b5c9c3b0ff653384ff7a14487899d8205975cd5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="asynctaskmethodbuilderlttresultgt-structure---internal-members"></a>AsyncTaskMethodBuilder&lt;TResult&gt; strukturu – vnitřní členy
Toto téma popisuje vnitřní členy <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> třídy. Obecné informace o této třídy, najdete v článku <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> referenční téma.  
  
 **Namespace:** <xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tyto vnitřní členy nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<TResult>  
       extends System.ValueType  
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder  
```  
  
## <a name="internal-members"></a>Vnitřní členy  
  
|Název|Popis|  
|----------|-----------------|  
|[Vlastnost ObjectIdForDebugger](../../extensibility/debugger/asynctaskmethodbuilder-tresult-objectidfordebugger-property.md)|Získá objekt, který se dá použít k jednoznačné identifikaci tohoto tvůrce pro ladicí program.|  
|[m_task pole](../../extensibility/debugger/asynctaskmethodbuilder-tresult-m-task-field.md)|Představuje líné inicializovaného vytvořené úloh.|  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601>   
 [Interní informace o paralelním rozšíření pro rozhraní .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
---
title: m_stateObject pole | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- m_stateObject field, Task class [.NET Framework debug engines]
ms.assetid: 68c54b22-3e1c-4031-b9c7-b972c519d8a0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 79313460d380b2b505f6fa75f35351811ddaa470
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="mstateobject-field"></a>m_stateObject pole
Objekt, který představuje data, která budou používat akce.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tento vnitřní člen nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.field assembly object m_stateObject  
```  
  
## <a name="remarks"></a>Poznámky  
 Toto je `state` parametr ve <xref:System.Threading.Tasks.Task.%23ctor%2A> konstruktor. Je také základní pole pro <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=fullName> vlastnost.  
  
## <a name="see-also"></a>Viz také  
 [Task – třída](../../extensibility/debugger/task-class-internal-members.md)
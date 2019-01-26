---
title: m_stateobject – pole | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- m_stateObject field, Task class [.NET Framework debug engines]
ms.assetid: 68c54b22-3e1c-4031-b9c7-b972c519d8a0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8718a45f0a2d8ef3075a9c390a756e3ec50062f9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55028709"
---
# <a name="mstateobject-field"></a>m_stateobject – pole
Objekt představující data, která bude používat akce.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v *mscorlib.dll*)  
  
 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.field assembly object m_stateObject  
```  
  
## <a name="remarks"></a>Poznámky  
 Toto je `state` parametr <xref:System.Threading.Tasks.Task.%23ctor%2A> konstruktoru. Je také pomocné pole <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=fullName> vlastnost.  
  
## <a name="see-also"></a>Viz také:  
 [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)
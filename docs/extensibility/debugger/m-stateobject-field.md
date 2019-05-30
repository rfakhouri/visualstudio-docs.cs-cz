---
title: m_stateobject – pole | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- m_stateObject field, Task class [.NET Framework debug engines]
ms.assetid: 68c54b22-3e1c-4031-b9c7-b972c519d8a0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 95947a1367ea1ddf4aa88689f731971d5c7d0a6c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66330834"
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
- [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)
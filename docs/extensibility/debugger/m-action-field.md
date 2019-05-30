---
title: m_action – pole | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- m_action field, Task class [.NET Framework debug engines]
ms.assetid: 201838c2-260d-4071-b6c3-f526874e19c9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d33d356f606dc2622647de53b50f5c677b3c14eb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66330982"
---
# <a name="maction-field"></a>m_action – pole
Delegát, který představuje kód pro spuštění v <xref:System.Threading.Tasks.Task> objektu.

 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **Sestavení:** mscorlib (v *mscorlib.dll*)

 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.

## <a name="syntax"></a>Syntaxe

```csharp
.field assembly object m_action
```

## <a name="remarks"></a>Poznámky
 Toto je `action` parametr <xref:System.Threading.Tasks.Task.%23ctor%2A> konstruktoru.

## <a name="see-also"></a>Viz také:
- [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)
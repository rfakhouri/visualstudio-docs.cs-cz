---
title: m_action – pole | Dokumentace Microsoftu
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
- m_action field, Task class [.NET Framework debug engines]
ms.assetid: 201838c2-260d-4071-b6c3-f526874e19c9
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 68d526fe4266f9c8f7c0d3dc4790c8b5893f72ea
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696194"
---
# <a name="maction-field"></a>m_action – pole
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [m_action – pole](https://docs.microsoft.com/visualstudio/extensibility/debugger/m-action-field).  
  
Delegát, který představuje kód pro spuštění v <xref:System.Threading.Tasks.Task> objektu.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v knihovně mscorlib.dll)  
  
 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.field assembly object m_action  
```  
  
## <a name="remarks"></a>Poznámky  
 Toto je `action` parametr <xref:System.Threading.Tasks.Task.%23ctor%2A> konstruktoru.  
  
## <a name="see-also"></a>Viz také  
 [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)


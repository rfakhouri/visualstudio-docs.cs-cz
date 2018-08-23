---
title: Třída ContingentProperties – vnitřní členy | Dokumentace Microsoftu
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
- ContingentProperties class [.NET Framework debug engines]
- debug engines, ContingentProperties class [.NET Framework]
ms.assetid: c49d1362-ab1c-4b6d-9950-fcae40e0e66b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 89152ddce5ffca798d57f5e96b817ed006105714
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676890"
---
# <a name="contingentproperties-class---internal-members"></a>Třída ContingentProperties – vnitřní členy
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [třída ContingentProperties – vnitřní členy](https://docs.microsoft.com/visualstudio/extensibility/debugger/contingentproperties-class-internal-members).  
  
Obsahuje další vlastnosti <xref:System.Threading.Tasks.Task> objektu.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v knihovně mscorlib.dll)  
  
 Protože tyto vnitřní členy nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.class auto ansi nested assembly beforefieldinit ContingentProperties  
       extends System.Object  
```  
  
## <a name="members"></a>Členové  
  
### <a name="fields"></a>Pole  
  
|Název|Popis|  
|----------|-----------------|  
|[m_children –](../../extensibility/debugger/m-children-field.md)|Seznam podřízených úloh, které jsou registrované s touto úlohou.|  
  
## <a name="remarks"></a>Poznámky  
 Rozhraní .NET Framework inicializuje pole této třídy, jenom když jsou potřeba.  
  
## <a name="see-also"></a>Viz také  
 [Interní informace o paralelním rozšíření pro rozhraní .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)


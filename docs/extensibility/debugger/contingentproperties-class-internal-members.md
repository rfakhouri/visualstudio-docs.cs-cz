---
title: "Třída ContingentProperties – vnitřní členy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ContingentProperties class [.NET Framework debug engines]
- debug engines, ContingentProperties class [.NET Framework]
ms.assetid: c49d1362-ab1c-4b6d-9950-fcae40e0e66b
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e1bd9c94b99b4881167d7ae434691ffd08666ced
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="contingentproperties-class---internal-members"></a>Třída ContingentProperties – vnitřní členy
Obsahuje další vlastnosti pro <xref:System.Threading.Tasks.Task> objektu.  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tyto vnitřní členy nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.class auto ansi nested assembly beforefieldinit ContingentProperties  
       extends System.Object  
```  
  
## <a name="members"></a>Členové  
  
### <a name="fields"></a>Pole  
  
|Název|Popis|  
|----------|-----------------|  
|[m_children](../../extensibility/debugger/m-children-field.md)|Seznam podřízené úlohy, které jsou registrované s touto úlohou.|  
  
## <a name="remarks"></a>Poznámky  
 Rozhraní .NET Framework inicializuje pole této třídy jenom v případě potřeby.  
  
## <a name="see-also"></a>Viz také  
 [Interní informace o paralelním rozšíření pro rozhraní .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
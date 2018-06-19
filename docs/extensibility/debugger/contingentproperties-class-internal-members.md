---
title: Třída ContingentProperties – vnitřní členy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ContingentProperties class [.NET Framework debug engines]
- debug engines, ContingentProperties class [.NET Framework]
ms.assetid: c49d1362-ab1c-4b6d-9950-fcae40e0e66b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b44bec34394df6f976416a827d7eb5d67cb99f6a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31097845"
---
# <a name="contingentproperties-class---internal-members"></a>Třída ContingentProperties – vnitřní členy
Obsahuje další vlastnosti pro <xref:System.Threading.Tasks.Task> objektu.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
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
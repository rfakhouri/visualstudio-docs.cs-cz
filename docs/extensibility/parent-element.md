---
title: Nadřazený Element | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Parent
- Parent element (VSCT XML schema)
ms.assetid: e4624ac8-1b9a-4940-910a-528a661cefad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 795654925a92f3e9ac0718e070e85c0f4f7f21c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137102"
---
# <a name="parent-element"></a>Nadřazený element
Nadřazený tohoto pole tlačítko nebo pole se seznamem může být pouze skupiny. Nadřazené nabídky nebo skupiny může být ostatní nabídky nebo skupiny. V [CommandPlacement Element](../extensibility/commandplacement-element.md), tento prvek je nutný; ve všech ostatních případech je volitelné. Pokud tento element je vynechán, nadřazeného `Group_Undefined:0` bude implicitní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Parent guid="guidMyCommandSet" id="MyParentGroupOrMenu" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno. Identifikátor GUID identifikátor GUID nebo ID příkazu.|  
|id|Požadováno. Identifikátor ID GUID nebo ID příkazu.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CommandTable – element](../extensibility/commandtable-element.md)|Definuje všechny elementy, které představují příkazy, které poskytuje VSPackage integrované vývojové prostředí (IDE). Například položky nabídky, nabídek, panely nástrojů a pole se seznamem.|  
|[Buttons – element](../extensibility/buttons-element.md)|Skupiny [Button Element](../extensibility/button-element.md) elementy.|  
|[Menus – element](../extensibility/menus-element.md)|Definuje všechny nabídky, které implementuje VSPackage.|  
|[Groups – element](../extensibility/groups-element.md)|Obsahuje položky, které definují příkaz skupiny VSPackage.|  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
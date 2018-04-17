---
title: CommandPlacement Element | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 2cbd7ac8-c55a-43d8-a26d-713b3d790016
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 14f28c8e2758d2dde9cf38db268abc9fa9b4f863
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="commandplacement-element"></a>CommandPlacement Element
CommandPlacement element umožňuje tlačítka, skupiny a nabídky mají být zahrnuty do více než jednu skupinu nebo nabídky. Pomocí elementu CommandPlacement nemáte zcela znovu definovat tyto položky k úpravě vzhledu uživatelské rozhraní.  
  
 Další informace najdete v tématu [vytváření skupin opakovaně použitelného z tlačítka](../extensibility/creating-reusable-groups-of-buttons.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<CommandPlacement guid=guidMyCommandSet" id="MyCommand" priority="0x001" >  
  <Parent>... </Parent>  
</CommandPlacement>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno. Identifikátor guid sadu příkazů, jak jsou definovány v [symboly Element](../extensibility/symbols-element.md).|  
|id|Požadováno. Id nabídky, skupinu nebo příkaz umístit, jak jsou definovány v `Symbols Element`.|  
|Priorita|Požadováno. Určuje pozici visual položky v jeho nadřazený element.|  
|Podmínka|Volitelné. V tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Nadřazené|Požadováno. Nabídky nebo skupiny, který je hostitelem položka, která má být umístěn.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CommandPlacements – element](../extensibility/commandplacements-element.md)|Určuje skupiny CommandPlacements a CommandPlacement elementů.|  
  
## <a name="example"></a>Příklad  
  
```  
<CommandPlacements>  
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0300">  
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>  
  </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="see-also"></a>Viz také  
 [CommandPlacements Element](../extensibility/commandplacements-element.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
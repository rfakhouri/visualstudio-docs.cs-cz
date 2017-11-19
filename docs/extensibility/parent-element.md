---
title: "Nadřazený Element | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Parent
- Parent element (VSCT XML schema)
ms.assetid: e4624ac8-1b9a-4940-910a-528a661cefad
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fc66e193b13ac6baf9d6089483a1281c2d6a59ef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
|[CommandTable Element](../extensibility/commandtable-element.md)|Definuje všechny elementy, které představují příkazy, které poskytuje VSPackage integrované vývojové prostředí (IDE). Například položky nabídky, nabídek, panely nástrojů a pole se seznamem.|  
|[Element tlačítka](../extensibility/buttons-element.md)|Skupiny [Button Element](../extensibility/button-element.md) elementy.|  
|[Element nabídky](../extensibility/menus-element.md)|Definuje všechny nabídky, které implementuje VSPackage.|  
|[Element skupiny](../extensibility/groups-element.md)|Obsahuje položky, které definují příkaz skupiny VSPackage.|  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
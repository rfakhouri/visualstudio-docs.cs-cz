---
title: Commandplacement – Element | Dokumentace Microsoftu
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
ms.openlocfilehash: c5da750b3f33127fdcfdf2e2a76d4df1556561b2
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2018
ms.locfileid: "39232426"
---
# <a name="commandplacement-element"></a>Commandplacement – element
Commandplacement – element umožňuje tlačítka, skupiny a nabídek, které mají být zahrnuty do více než jedné skupině nebo v nabídce. Pomocí commandplacement – element nemáte zcela předefinovat tyto položky, aby bylo možné změnit vzhled uživatelského rozhraní.  
  
 Další informace najdete v tématu [vytváření znovu použitelných skupin tlačítek](../extensibility/creating-reusable-groups-of-buttons.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<CommandPlacement guid="guidMyCommandSet" id="MyCommand" priority="0x001" >  
  <Parent>... </Parent>  
</CommandPlacement>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|identifikátor GUID|Požadováno. Identifikátor guid sady příkazů, jak jsou definovány v [Symbols – element](../extensibility/symbols-element.md).|  
|id|Požadováno. Id nabídky, skupiny nebo příkaz, který byl umístěn, jak jsou definovány v `Symbols Element`.|  
|Priorita|Požadováno. Určuje vizuální umístění položky v svého nadřízeného elementu.|  
|Podmínka|Volitelné. Zobrazit [podmíněného Aattributes](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené prvky  
  
|Prvek|Popis|  
|-------------|-----------------|  
|nadřazené|Požadováno. Nabídky nebo skupiny, který je hostitelem položka, která má být umístěn.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Commandplacements – element](../extensibility/commandplacements-element.md)|Určuje skupiny commandplacements – a commandplacement – prvků.|  
  
## <a name="example"></a>Příklad  
  
```  
<CommandPlacements>  
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0300">  
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>  
  </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Commandplacements – element](../extensibility/commandplacements-element.md)   
 [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

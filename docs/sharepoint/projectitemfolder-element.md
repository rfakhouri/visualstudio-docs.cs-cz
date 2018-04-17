---
title: ProjectItemFolder – Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItemFolder element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 25d126ab05edccf44642271ed7e379988defe212
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="projectitemfolder-element"></a>ProjectItemFolder – element
  Představuje mapované složky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectItemFolder Target = "Path of SharePoint folder the mapped folder corresponds to"  
    Type = "Type of deployment for the mapped folder" />  
```  
  
## <a name="type"></a>Typ  
 **ProjectItemFolderType**  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|**cíl**|Požadované **xs:string** atribut.<br /><br /> Cesta ke složce v instalaci služby SharePoint, které mapované složky odpovídá relativní vzhledem ke kořenové složce nasazení. Nasazení kořenové složky je určen podle typu nasazení určeného **typ** atribut.<br /><br /> Další informace najdete v popisech pro **Cesta nasazení** a **nasazení kořenové** projektu služby SharePoint položky v [vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
|**Typ**|Požadované **xs:string** atribut.<br /><br /> Typ nasazení pro mapované složky. Další informace o možných hodnot, viz popis **typ nasazení** vlastnosti položky projektu služby SharePoint v [vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItem –](../sharepoint/projectitem-element.md)|Představuje položky projektu služby SharePoint. Toto je požadovaný kořenový element .spdata souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o mapované složky najdete v tématu [postupy: Přidání a odebrání mapované složky](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|**obor názvů**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Postupy: Přidání a odebrání mapovaných složek](../sharepoint/how-to-add-and-remove-mapped-folders.md)  
  
  
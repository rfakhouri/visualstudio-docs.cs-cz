---
title: ProjectItemFolder – Element | Dokumentace Microsoftu
ms.date: 02/02/2017
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
ms.openlocfilehash: fdecca0b987efd22d4ddd9d3555ede2601b8205e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53855618"
---
# <a name="projectitemfolder-element"></a>ProjectItemFolder – element
  Představuje mapované složky.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
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
|**Cíl**|Vyžaduje **xs: řetězec** atribut.<br /><br /> Cesta ke složce v instalaci služby SharePoint, která mapovaná složka odpovídá vzhledem ke kořenové složky nasazení. Kořenové složky nasazení se určuje podle typ nasazení určený **typ** atribut.<br /><br /> Další informace najdete v popisech pro **cesty nasazení** a **kořen nasazení** položky v projektu služby SharePoint [řešení pro vývoj SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
|**Typ**|Vyžaduje **xs:string** atribut.<br /><br /> Typ nasazení pro mapovanou složku. Další informace o možných hodnot, viz popis **typ nasazení** vlastnosti položky projektu služby SharePoint v [řešení vývoj služby SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Podřízené prvky
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené prvky
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItem –](../sharepoint/projectitem-element.md)|Představuje položku Sharepointového projektu. Tento element je požadovaný kořenový element *.spdata* souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o mapované složky najdete v tématu [postupy: Přidání a odebrání mapovaných složek](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
## <a name="element-information"></a>Informace o elementu
  
|||  
|-|-|  
|**Namespace**|http<nolink>: //schemas.microsoft.com/VisualStudio/2010/<br>SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu služby SharePoint|  
|**Soubor ověření**|ProjectItemModelSchema.xsd|  
|**Může být prázdný**|Ne|  
  
## <a name="see-also"></a>Viz také:
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Postupy: Přidání a odebrání mapovaných složek](../sharepoint/how-to-add-and-remove-mapped-folders.md)  

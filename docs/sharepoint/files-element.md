---
title: Soubory Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Files element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d75041c1b0202eecd5769773efbcfce9c53ec4ef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="files-element"></a>Element Soubory
  Určuje soubory k nasazení s položkou projektu služby SharePoint, jako je například souborů funkcí a výstup závislé jiné-projektů služby SharePoint.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Files>  
  <ProjectItemFile.../>  
  <ProjectOutputFile.../>  
</Files>  
```  
  
## <a name="type"></a>Typ  
 **FileCollectionType**  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItemFile –](../sharepoint/projectitemfile-element.md)|Volitelné **ProjectItemFileType** element.<br /><br /> Představuje soubor SharePoint, jako je například soubor prvku funkce zahrnout s položkou projektu při nasazení do služby SharePoint.|  
|[ProjectOutputFile –](../sharepoint/projectoutputfile-element.md)|Volitelné **ProjectOutputFileType** element.<br /><br /> Představuje výstup projektu zahrnout s položkou projektu při nasazení do služby SharePoint.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItem –](../sharepoint/projectitem-element.md)|Představuje položky projektu služby SharePoint. Toto je požadovaný kořenový element .spdata souboru.|  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|**obor názvů**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  
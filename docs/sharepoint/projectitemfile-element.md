---
title: ProjectItemFile – Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItemFile element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 67d1ed00ef4781e0419d1fceda5f95a8c0c710fb
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="projectitemfile-element"></a>ProjectItemFile – element
  Představuje soubor SharePoint, jako je například soubor prvku funkce zahrnout s položkou projektu při nasazení do služby SharePoint.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<ProjectItemFile Source = "Name of the file"  
    Target = "Deployment path of the file"  
    Type = "Type of deployment for the file" />  
```  
  
## <a name="type"></a>Typ  
 **ProjectItemFileType**  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|**Zdroj**|Požadované **xs:string** atribut.<br /><br /> Název souboru pro nasazení s položkou projektu.|  
|**cíl**|Volitelné **xs:string** atribut.<br /><br /> Cesta, kde bude nasazen soubor na webu služby SharePoint, relativní vzhledem ke kořenové složce nasazení. Nasazení kořenové složky je určen podle typu nasazení určeného **typ** atribut. Pokud **cíl** atribut nezadá, soubor se nasadí do složky s názvem zadaným v **zdroj** atribut.<br /><br /> Další informace najdete v popisech pro **Cesta nasazení** a **nasazení kořenové** projektu služby SharePoint položky v [vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
|**Typ**|Požadované **xs:string** atribut.<br /><br /> Typ nasazení pro soubor. Další informace o možných hodnot, viz popis **typ nasazení** vlastnosti položky projektu služby SharePoint v [vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Soubory](../sharepoint/files-element.md)|Určuje soubory, které chcete zahrnout do položky projektu služby SharePoint, když se nasadí do služby SharePoint.|  
  
## <a name="remarks"></a>Poznámky  
 Soubory služby SharePoint, které jsou obvykle odkazované ve **ProjectItemFile –** prvky patří souborů funkcí (Elements.xml), soubory schématu pro seznam definic (Schema.xml) a soubory definice webových částí pro webové části (.webpart).  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|**obor názvů**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  
---
title: Soubory Element | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: Files element
ms.assetid: 3c611d5b-28f1-48a7-a068-63e01fa2f3aa
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 28c8bfc8f0c986eda6697e8d6ed841a0e177c694
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  
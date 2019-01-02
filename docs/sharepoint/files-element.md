---
title: Soubory Element | Dokumentace Microsoftu
ms.date: 02/02/2017
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
ms.openlocfilehash: e27e3192ec0d9a312c3cfc0a3521daf534c68e9a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53922302"
---
# <a name="files-element"></a>Files – element
  Určuje soubory, které chcete nasadit položky projektu služby SharePoint, jako je například souborů elementu funkce a výstupu závislé jiné-projektů služby SharePoint.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
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
  
### <a name="child-elements"></a>Podřízené prvky
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItemFile –](../sharepoint/projectitemfile-element.md)|Volitelné **ProjectItemFileType** elementu.<br /><br /> Představuje soubor služby SharePoint, jako je například soubor prvku funkce zahrnout do položky projektu při nasazení do služby SharePoint.|  
|[ProjectOutputFile –](../sharepoint/projectoutputfile-element.md)|Volitelné **ProjectOutputFileType** elementu.<br /><br /> Představuje výstupní projekt, který patří do položky projektu při nasazení do služby SharePoint.|  
  
### <a name="parent-elements"></a>Nadřazené prvky
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItem –](../sharepoint/projectitem-element.md)|Představuje položku Sharepointového projektu. Tento prvek požadovaný kořenový element z `.spdata` souboru.|  
  
## <a name="element-information"></a>Informace o elementu
  
|||  
|-|-|  
|**Namespace**|http<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu služby SharePoint|  
|**Soubor ověření**|ProjectItemModelSchema.xsd|  
|**Může být prázdný**|Ne|  
  
## <a name="see-also"></a>Viz také:
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)  

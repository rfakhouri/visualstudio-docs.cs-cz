---
title: Soubory Element | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Files element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b25bb220d3c22af280a486de115193af38c85dbe
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54864524"
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
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|Volitelné **ProjectItemFileType** elementu.<br /><br /> Představuje soubor služby SharePoint, jako je například soubor prvku funkce zahrnout do položky projektu při nasazení do služby SharePoint.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|Volitelné **ProjectOutputFileType** elementu.<br /><br /> Představuje výstupní projekt, který patří do položky projektu při nasazení do služby SharePoint.|  
  
### <a name="parent-elements"></a>Nadřazené prvky
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Představuje položku Sharepointového projektu. Tento prvek požadovaný kořenový element z `.spdata` souboru.|  
  
## <a name="element-information"></a>Informace o elementu
  
|||  
|-|-|  
|**Namespace**|http<nolink>://schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu služby SharePoint|  
|**Soubor ověření**|ProjectItemModelSchema.xsd|  
|**Může být prázdný**|Ne|  
  
## <a name="see-also"></a>Viz také:
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)  

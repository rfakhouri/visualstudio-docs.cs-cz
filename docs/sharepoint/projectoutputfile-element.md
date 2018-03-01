---
title: "ProjectOutputFile – Element | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectOutputFile element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 5b57f00960629d65f264f22532a16202d6ae5d7a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="projectoutputfile-element"></a>ProjectOutputFile – element
  Představuje výstup samostatné projektu zahrnout s položkou projektu při nasazení do služby SharePoint.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectOutputFile ProjectId = "GUID of the project"  
    ProjectPath = "Relative path of the project"  
    Target = "Deployment path of the project output"  
    Type = "Type of deployment for the project output" />  
```  
  
## <a name="type"></a>Typ  
 **ProjectOutputFileType**  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|**ProjectId**|Požadované **xs:string** atribut.<br /><br /> Identifikátor GUID závislého projektu, který má výstup, které chcete zahrnout. To odpovídá **ProjectGuid** element v souboru projektu závislé.|  
|**ProjectPath**|Požadované **xs:string** atribut.<br /><br /> Relativní cesta, včetně názvu souboru projektu závislého projektu, který má výstup, který chcete zahrnout. Tato cesta je relativní vzhledem ke kořenové složce projektu služby SharePoint, který obsahuje položky projektu služby SharePoint.|  
|**Cíl**|Volitelné **xs:string** atribut.<br /><br /> Cestu k umístění výstupu závislé projektu k nasazení na serveru SharePoint, která je relativní vzhledem ke kořenové složce nasazení. Nasazení kořenové složky je určen podle typu nasazení určeného **typ** atribut.<br /><br /> Další informace najdete v popisech pro **Cesta nasazení** a **nasazení kořenové** projektu služby SharePoint položky v [vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
|**Typ**|Požadované **xs:string** atribut.<br /><br /> Typ nasazení pro výstup závislé projektu. Další informace o možných hodnot, viz popis **typ nasazení** vlastnosti položky projektu služby SharePoint v [vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Soubory](../sharepoint/files-element.md)|Určuje soubory, které chcete zahrnout do položky projektu služby SharePoint, když se nasadí do služby SharePoint.|  
  
## <a name="remarks"></a>Poznámky  
 Použití **ProjectOutputFile** elementu, který chcete zahrnout výstup projektu nasazení položky projektu služby SharePoint. Můžete zadat jiný projekt, nebo stejný projekt, který obsahuje položky projektu. Další informace najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Poskytnutí balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  
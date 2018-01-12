---
title: "FeatureProperties – Element | Microsoft Docs"
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
helpviewer_keywords: FeatureProperties element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e710c5a73fbee0a09fb69518def1b03e353661c8
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="featureproperties-element"></a>FeatureProperties – element
  Reprezentuje kolekci hodnot vlastností, které jsou součástí funkce při nasazení do služby SharePoint. Po nasazení funkce můžete přistupovat hodnoty vlastností v kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<FeatureProperties>  
  <FeatureProperty.../>  
</FeatureProperties>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[FeatureProperty –](../sharepoint/featureproperty-element.md)|Volitelný element.<br /><br /> Představuje vlastní vlastnost, ve formátu klíč/hodnota.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItem –](../sharepoint/projectitem-element.md)|Představuje položky projektu služby SharePoint. Toto je požadovaný kořenový element .spdata souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o vlastnosti funkcí najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Informace o elementu  
  
|Prvek|Popis|  
|-------------|-----------------|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Poskytování informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  
---
title: FeatureProperties – Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperties element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ee33d880a56103ea024f22038350ec36021561b
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691785"
---
# <a name="featureproperties-element"></a>FeatureProperties – element
  Kolekce hodnot vlastností, které jsou součástí funkce při nasazení do služby SharePoint. Po nasazení funkce můžete přistupovat hodnoty vlastností v kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
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
|[ProjectItem –](../sharepoint/projectitem-element.md)|Představuje položky projektu služby SharePoint. Tento element požadovaný kořenový element z `.spdata` souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o vlastnosti funkcí najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Informace o elementu  
  
|Prvek|Popis|  
|-------------|-----------------|  
|**obor názvů**|http<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010 nebo SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Poskytování informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  
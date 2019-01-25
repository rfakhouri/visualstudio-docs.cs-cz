---
title: FeatureProperties – Element | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperties element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fb345e66a53f9816281df6e948a8961252c0fcea
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54862586"
---
# <a name="featureproperties-element"></a>FeatureProperties – element
  Kolekce hodnot vlastností, které jsou součástí funkce, když se nasadí do služby SharePoint. Po nasazení funkce můžete přistupovat hodnoty vlastností v kódu.  
  
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
  
### <a name="child-elements"></a>Podřízené prvky
  
|Prvek|Popis|  
|-------------|-----------------|  
|[FeatureProperty](../sharepoint/featureproperty-element.md)|Volitelný element.<br /><br /> Představuje vlastní vlastnosti ve formátu klíč/hodnota.|  
  
### <a name="parent-elements"></a>Nadřazené prvky
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Představuje položku Sharepointového projektu. Tento prvek požadovaný kořenový element z `.spdata` souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o vlastnosti funkce, najdete v části [poskytují informace o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Informace o elementu
  
|Prvek|Popis|  
|-------------|-----------------|  
|**Namespace**|http<nolink>://schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu služby SharePoint|  
|**Soubor ověření**|ProjectItemModelSchema.xsd|  
|**Může být prázdný**|Ne|  
  
## <a name="see-also"></a>Viz také:
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Zadání informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  

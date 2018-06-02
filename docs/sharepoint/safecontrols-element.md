---
title: SafeControls – Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SafeControls element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 85b0d1884812c4846d78804b34d50986140bf29e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692025"
---
# <a name="safecontrols-element"></a>SafeControls – element
  Kolekce ovládacích prvků ASPX a webových částí, které jsou označeny jako bezpečné pro všechny uživatele pro přístup na všechny stránky ASPX na webu služby SharePoint.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<SafeControls>  
  <SafeControl.../>  
</SafeControls>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[SafeControl –](../sharepoint/safecontrol-element.md)|Volitelný element.<br /><br /> Představuje prvek ASPX nebo webovou část, která je označeny jako bezpečné pro všechny uživatele pro přístup na všechny stránky ASPX na webu služby SharePoint.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItem –](../sharepoint/projectitem-element.md)|Představuje položky projektu služby SharePoint. Tento element požadovaný kořenový element z `.spdata` souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o bezpečné ovládací prvky najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|**obor názvů**|http<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010 nebo SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Poskytování informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  
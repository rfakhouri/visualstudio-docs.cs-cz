---
title: SafeControls – Element | Dokumentace Microsoftu
ms.date: 02/02/2017
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
ms.openlocfilehash: e08b414858db389e507dc9395d218807c9530db6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53875965"
---
# <a name="safecontrols-element"></a>SafeControls – element
  Určuje kolekci ASPX a webové části, které jsou určené jako zabezpečení pro všechny uživatele pro přístup na libovolné stránce ASPX na webu služby SharePoint.  
  
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
  
### <a name="child-elements"></a>Podřízené prvky
  
|Prvek|Popis|  
|-------------|-----------------|  
|[SafeControl –](../sharepoint/safecontrol-element.md)|Volitelný element.<br /><br /> Představuje prvek ASPX nebo webovou část, která je označena jako bezpečná pro všechny uživatele pro přístup na libovolné stránce ASPX na webu služby SharePoint.|  
  
### <a name="parent-elements"></a>Nadřazené prvky
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectItem –](../sharepoint/projectitem-element.md)|Představuje položku Sharepointového projektu. Tento prvek požadovaný kořenový element z *.spdata* souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o bezpečné ovládací prvky najdete v tématu [poskytují informace o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Informace o elementu
  
|||  
|-|-|  
|**Namespace**|http<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu služby SharePoint|  
|**Soubor ověření**|ProjectItemModelSchema.xsd|  
|**Může být prázdný**|Ne|  
  
## <a name="see-also"></a>Viz také:
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Zadání informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  

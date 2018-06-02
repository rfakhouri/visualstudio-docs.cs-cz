---
title: SafeControl – Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SafeControl element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5e507d83a1f1f75e346ccbab1858d797dc7b7518
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691840"
---
# <a name="safecontrol-element"></a>SafeControl – element
  Představuje prvek ASPX nebo webovou část, která je označeny jako bezpečné pro všechny uživatele pro přístup na všechny stránky ASPX na webu služby SharePoint.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<SafeControl Assembly = "Name of assembly that contains the safe control"  
    IsSafe = "true/false"  
    IsSafeAgainstScript = "true/false"  
    Name = "Name of this safe control entry"  
    Namespace = "Namespace of the safe control"  
    TypeName = "Type of the safe control" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|**Assembly**|Volitelné **xs:string** atribut.<br /><br /> Název sestavení, ve kterém je definovaný prvek ASPX nebo webové části. Ve výchozím nastavení používá tento atribut **$SharePoint.Project.AssemblyFullName$** nahraditelný parametr pro název sestavení. Další informace najdete v tématu [nahraditelné parametry](../sharepoint/replaceable-parameters.md).|  
|**IsSafe**|Volitelné **xs:boolean** atribut.<br /><br /> Určuje, jestli je zabezpečený nedůvěryhodným uživatelům přístup k řízení ASPX nebo webové části.|  
|**IsSafeAgainstScript**|Volitelné **xs:boolean** atribut.<br /><br /> Určuje, zda nedůvěryhodným uživatelům můžete zobrazit nebo upravit vlastnosti ASPX řízení nebo webové části.|  
|**Jméno**|Volitelné **xs:string** atribut.<br /><br /> Název této položky bezpečné ovládací prvek v kolekci.|  
|**obor názvů**|Volitelné **xs:string** atribut.<br /><br /> Obor názvů řízení ASPX nebo webové části.|  
|**TypeName**|Volitelné **xs:string** atribut.<br /><br /> Název typu ovládacího prvku ASPX nebo webové části.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[SafeControls –](../sharepoint/safecontrols-element.md)|Představuje kolekci ovládacích prvků ASPX a webových částí, které jsou označeny jako bezpečné pro všechny uživatele pro přístup na všechny stránky ASPX na webu služby SharePoint.|  
  
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
  
  
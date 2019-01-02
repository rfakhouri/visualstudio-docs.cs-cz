---
title: ExtensionDataItem – Element | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ExtensionDataItem element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d95459be48b6d5e87b1a312e68e6ebea2645cb29
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916936"
---
# <a name="extensiondataitem-element"></a>ExtensionDataItem – element
  Vlastní datová položka, která je přidružená k položce projektu služby SharePoint, ve formátu klíč/hodnota. Klíč a hodnotu musí být řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<ExtensionDataItem Key = "Key of the data item"  
    Value = "Value of the data item" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|**Key**|Vyžaduje **xs: řetězec** atribut.<br /><br /> Klíč, který se používá k ukládání a načítání datová položka.|  
|**Hodnota**|Vyžaduje **xs:string** atribut.<br /><br /> Hodnota datová položka.|  
  
### <a name="child-elements"></a>Podřízené prvky
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené prvky
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ExtensionData –](../sharepoint/extensiondata-element.md)|Představuje kolekci vlastních datových položek, které jsou spojeny s položku Sharepointového projektu.|  
  
## <a name="remarks"></a>Poznámky  
 Po přidružení vlastních dat k položky Sharepointového projektu s použitím <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> objektu, Visual Studio uloží data do nového **ExtensionDataItem –** element v `.spdata` souboru Položka projektu. Další informace najdete v tématu [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
## <a name="element-information"></a>Informace o elementu
  
|||  
|-|-|  
|**Namespace**|http<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel| 
|**Název schématu**|Schéma položky projektu služby SharePoint|  
|**Soubor ověření**|ProjectItemModelSchema.xsd|  
|**Může být prázdný**|Ne|  
  
## <a name="see-also"></a>Viz také:
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)  

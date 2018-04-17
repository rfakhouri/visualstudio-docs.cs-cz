---
title: ExtensionDataItem – Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
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
ms.openlocfilehash: 8c991d3fece3e5997e8d470d168af9eba47c8663
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="extensiondataitem-element"></a>ExtensionDataItem – element
  Představuje položku vlastní data, která je přidružená k položce projektu služby SharePoint, ve formátu klíč/hodnota. Klíč i hodnota musí být řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ExtensionDataItem Key = "Key of the data item"  
    Value = "Value of the data item" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|**Key**|Požadované **xs:string** atribut.<br /><br /> Klíč, který se používá k ukládání a načítání datová položka.|  
|**Hodnota**|Požadované **xs:string** atribut.<br /><br /> Hodnota datová položka.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ExtensionData –](../sharepoint/extensiondata-element.md)|Představuje kolekci vlastních datových položek, které jsou přidružené položky projektu služby SharePoint.|  
  
## <a name="remarks"></a>Poznámky  
 Když přidružení vlastních dat k položky projektu služby SharePoint pomocí <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> objektu, Visual Studio uloží data do nové **ExtensionDataItem –** element v souboru .spdata pro položku projektu. Další informace najdete v tématu [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|**obor názvů**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  
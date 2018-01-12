---
title: "Referenční dokumentace schématu položek projektu služby SharePoint | Microsoft Docs"
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
helpviewer_keywords:
- FeatureProperty element
- SafeControls element
- SafeControl element
- .spdata files
- ExtensionData element
- FeatureProperties element
- ProjectOutputFile element
- Files element
- ProjectItemFolder element
- ProjectItemFile element
- ExtensionDataItem element
- ProjectItem element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 99a2471919483f02a9f58a35ad164527a12a39c5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="sharepoint-project-item-schema-reference"></a>Referenční dokumentace schématu položek projektu SharePoint
  Visual Studio používá k ověření obsahu soubory .spdata schéma položky projektu služby SharePoint. Soubor .spdata určuje obsahu a chování položky projektu služby SharePoint. Další informace o obsahu SharePoint – položky projektu najdete v tématu [vytváření šablon položek a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Schéma položky projektu služby SharePoint je ProjectItemModelSchema.xsd a je nainstalována ve výchozím nastavení v % Program Files (11.0\Xml\Schemas x86)%\Microsoft Visual Studio.  
  
 Kořenový element [ProjectItem](../sharepoint/projectitem-element.md) elementu. Následující tabulka popisuje všechny prvky definované schéma.  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ExtensionData –](../sharepoint/extensiondata-element.md)|Představuje kolekci vlastních datových položek, které jsou přidružené položky projektu služby SharePoint.|  
|[ExtensionDataItem –](../sharepoint/extensiondataitem-element.md)|Představuje položku vlastní data, která je přidružená k položce projektu služby SharePoint, ve formátu klíč/hodnota. Klíč i hodnota musí být řetězce.|  
|[FeatureProperties –](../sharepoint/featureproperties-element.md)|Reprezentuje kolekci hodnot vlastností, které jsou součástí funkce při nasazení do služby SharePoint. Po nasazení funkce můžete přistupovat hodnoty vlastností v kódu.|  
|[FeatureProperty –](../sharepoint/featureproperty-element.md)|Představuje vlastní vlastnost, která je součástí funkce při nasazení do služby SharePoint. Po nasazení funkce, můžete přejít vlastnost v kódu.|  
|[Soubory](../sharepoint/files-element.md)|Určuje soubory k nasazení do položky projektu služby SharePoint, jako je například soubor prvku funkce nebo výstup projektu.|  
|[ProjectItem –](../sharepoint/projectitem-element.md)|Představuje položky projektu služby SharePoint.|  
|[ProjectItemFile –](../sharepoint/projectitemfile-element.md)|Představuje soubor SharePoint, jako je například soubor prvku funkce zahrnout s položkou projektu při nasazení do služby SharePoint.|  
|[ProjectItemFolder –](../sharepoint/projectitemfolder-element.md)|Představuje mapované složky.|  
|[ProjectOutputFile –](../sharepoint/projectoutputfile-element.md)|Představuje výstup projektu zahrnout s položkou projektu při nasazení do služby SharePoint.|  
|[SafeControl –](../sharepoint/safecontrol-element.md)|Představuje prvek ASPX nebo webovou část, která je označeny jako bezpečné pro všechny uživatele pro přístup na všechny stránky ASPX na webu služby SharePoint.|  
|[SafeControls –](../sharepoint/safecontrols-element.md)|Představuje kolekci ovládacích prvků ASPX a webových částí, které jsou označeny jako bezpečné pro všechny uživatele pro přístup na všechny stránky ASPX na webu služby SharePoint.|  
  
## <a name="see-also"></a>Viz také  
 [Vytváření šablon položek a projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)  
  
  
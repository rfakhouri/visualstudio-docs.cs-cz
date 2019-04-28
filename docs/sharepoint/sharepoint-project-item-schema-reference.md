---
title: Referenční dokumentace schématu položek projektu služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bc15ff5c384ec63f99ed50a5f3c700efd7ba3c18
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63007716"
---
# <a name="sharepoint-project-item-schema-reference"></a>Referenční dokumentace schématu položek projektu služby SharePoint
  Visual Studio používá k ověření obsahu schématu položek projektu služby SharePoint *.spdata* soubory. *.Spdata* Určuje soubor obsahu a chování položky Sharepointového projektu. Další informace o obsahu položky Sharepointového projektu naleznete v tématu [položky vytvářet šablony a šablony projektů pro položky Sharepointového projektu](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).

 Schéma položky projektu služby SharePoint je ProjectItemModelSchema.xsd a je nainstalovaná ve výchozím nastavení v % Program Files (11.0\Xml\Schemas x86)%\Microsoft sady Visual Studio.

 Kořenový prvek je [ProjectItem](../sharepoint/projectitem-element.md) elementu. Následující tabulka popisuje všechny prvky definovaná pomocí schématu rozhraní.

|Prvek|Popis|
|-------------|-----------------|
|[ExtensionData](../sharepoint/extensiondata-element.md)|Představuje kolekci vlastních datových položek, které jsou spojeny s položku Sharepointového projektu.|
|[ExtensionDataItem](../sharepoint/extensiondataitem-element.md)|Představuje položku vlastní data, která je přidružená k položce projektu služby SharePoint, ve formátu klíč/hodnota. Klíč a hodnotu musí být řetězce.|
|[FeatureProperties](../sharepoint/featureproperties-element.md)|Reprezentuje kolekci hodnot vlastností, které jsou součástí funkce, když se nasadí do služby SharePoint. Po nasazení funkce můžete přistupovat hodnoty vlastností v kódu.|
|[FeatureProperty](../sharepoint/featureproperty-element.md)|Představuje vlastní vlastnost, která je součástí funkce, když se nasadí do služby SharePoint. Po nasazení funkce můžete přistupovat k vlastnosti v kódu.|
|[Soubory](../sharepoint/files-element.md)|Určuje soubory, které chcete nasadit do položky projektu služby SharePoint, jako je například soubor elementu na funkce nebo výstup projektu.|
|[ProjectItem](../sharepoint/projectitem-element.md)|Představuje položku Sharepointového projektu.|
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|Představuje soubor služby SharePoint, jako je například soubor prvku funkce zahrnout do položky projektu při nasazení do služby SharePoint.|
|[ProjectItemFolder](../sharepoint/projectitemfolder-element.md)|Představuje mapované složky.|
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|Představuje výstupní projekt, který patří do položky projektu při nasazení do služby SharePoint.|
|[SafeControl](../sharepoint/safecontrol-element.md)|Představuje prvek ASPX nebo webovou část, která je označena jako bezpečná pro všechny uživatele pro přístup na libovolné stránce ASPX na webu služby SharePoint.|
|[SafeControls –](../sharepoint/safecontrols-element.md)|Představuje kolekci ovládacích prvcích ASPX a webových částech, které jsou označeny jako bezpečné pro všechny uživatele pro přístup na libovolné stránce ASPX na webu služby SharePoint.|

## <a name="see-also"></a>Viz také:
- [Vytváření šablon položek a projektů pro položky projektu SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)

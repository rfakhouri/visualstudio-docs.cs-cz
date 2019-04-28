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
ms.openlocfilehash: 6860a91067daa6da1d4223ae5060385087ad3433
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967328"
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
|**Namespace**|http:\/\/schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**Název schématu**|Schéma položky projektu služby SharePoint|
|**Soubor ověření**|ProjectItemModelSchema.xsd|
|**Může být prázdný**|Ne|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)
- [Zadání informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)

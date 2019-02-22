---
title: FeatureProperty – Element | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperty element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4bf3cbb84c32fdb3f5eba7ba8706c1035b1d9019
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56633470"
---
# <a name="featureproperty-element"></a>FeatureProperty – element
  Představuje vlastní vlastnost, která je součástí funkce, když se nasadí do služby SharePoint. Po nasazení funkce můžete přistupovat k vlastnosti v kódu.

## <a name="syntax"></a>Syntaxe

```xml
<FeatureProperty Key = "Key of the property value"
    Value = "Property value" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|**Key**|Vyžaduje **xs:string** atribut.<br /><br /> Klíč, který se používá k ukládání a načítání hodnoty vlastnosti. Každou vlastnost musí mít klíč, který je jedinečný v rámci funkce.|
|**Hodnota**|Vyžaduje **xs:string** atribut.<br /><br /> Hodnota vlastnosti.|

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[FeatureProperties](../sharepoint/featureproperties-element.md)|Reprezentuje kolekci hodnot vlastností, které jsou součástí funkce, když se nasadí do služby SharePoint.|

## <a name="remarks"></a>Poznámky
 Další informace o vlastnosti funkce, najdete v části [poskytování informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).

## <a name="element-information"></a>Informace o elementu

|||
|-|-|
|**Namespace**|http<nolink>://schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**Název schématu**|Schéma položky projektu služby SharePoint|
|**Soubor ověření**|ProjectItemModelSchema.xsd|
|**Může být prázdný**|Ne|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)
- [Zadání informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)

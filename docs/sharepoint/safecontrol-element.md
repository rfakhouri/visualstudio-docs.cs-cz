---
title: SafeControl – Element | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SafeControl element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e6b47254a80c9cdadab6ca18f2fb8c3e8540fbd0
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/21/2019
ms.locfileid: "58324562"
---
# <a name="safecontrol-element"></a>SafeControl – element
  Představuje prvek ASPX nebo webovou část, která je označena jako bezpečná pro všechny uživatele pro přístup na libovolné stránce ASPX na webu služby SharePoint.

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
|**Assembly**|Volitelné **xs:string** atribut.<br /><br /> Název sestavení, ve kterém je definována ASPX ovládací prvek nebo webovou část. Ve výchozím nastavení, používá tento atribut **$SharePoint.Project.AssemblyFullName$** proměnnou pro název sestavení. Další informace najdete v tématu [nahraditelné parametry](../sharepoint/replaceable-parameters.md).|
|**IsSafe**|Volitelné **xs:boolean** atribut.<br /><br /> Určuje, zda ovládací prvek ASPX nebo webovou část nedůvěryhodným uživatelům přístup k zabezpečené.|
|**IsSafeAgainstScript**|Volitelné **xs:boolean** atribut.<br /><br /> Určuje, zda nedůvěryhodným uživatelům můžete zobrazit nebo upravit vlastnosti ovládacího prvku ASPX nebo webovou část.|
|**Název**|Volitelné **xs:string** atribut.<br /><br /> Název této položky bezpečný ovládací prvek v kolekci.|
|**Namespace**|Volitelné **xs:string** atribut.<br /><br /> Obor názvů ovládacího prvku ASPX nebo webovou část.|
|**TypeName**|Volitelné **xs:string** atribut.<br /><br /> Název typu ovládacího prvku ASPX nebo webovou část.|

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[SafeControls –](../sharepoint/safecontrols-element.md)|Představuje kolekci ovládacích prvcích ASPX a webových částech, které jsou označeny jako bezpečné pro všechny uživatele pro přístup na libovolné stránce ASPX na webu služby SharePoint.|

## <a name="remarks"></a>Poznámky
 Další informace o bezpečné ovládací prvky najdete v tématu [poskytují informace o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).

## <a name="element-information"></a>Informace o elementu

|||
|-|-|
|**Namespace**|http:\/\/schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**Název schématu**|Schéma položky projektu služby SharePoint|
|**Soubor ověření**|ProjectItemModelSchema.xsd|
|**Může být prázdný**|Ne|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)
- [Zadání informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)

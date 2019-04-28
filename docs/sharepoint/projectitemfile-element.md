---
title: ProjectItemFile – Element | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItemFile element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 57c491c79030eea1a01024235c01aec425d5994c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62562359"
---
# <a name="projectitemfile-element"></a>ProjectItemFile – element
  Představuje soubor služby SharePoint, jako je například soubor prvku funkce zahrnout do položky projektu při nasazení do služby SharePoint.

## <a name="syntax"></a>Syntaxe

```xml
<ProjectItemFile Source = "Name of the file"
    Target = "Deployment path of the file"
    Type = "Type of deployment for the file" />
```

## <a name="type"></a>Type
 **ProjectItemFileType**

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|**Zdroj**|Vyžaduje **xs:string** atribut.<br /><br /> Název souboru, který má nasazení s položkou projektu.|
|**Cíl**|Volitelné **xs:string** atribut.<br /><br /> Cesta, kam se nasadí soubor na Sharepointu, vzhledem ke kořenové složky nasazení. Kořenové složky nasazení se určuje podle typ nasazení určený **typ** atribut. Pokud **cílové** atribut není zadán, soubor bude nasazen do složky s názvem zadaným v **zdroj** atribut.<br /><br /> Další informace najdete v popisech pro **cesty nasazení** a **kořen nasazení** položky v projektu služby SharePoint [řešení pro vývoj SharePoint](../sharepoint/developing-sharepoint-solutions.md).|
|**Typ**|Vyžaduje **xs:string** atribut.<br /><br /> Typ nasazení k souboru. Další informace o možných hodnot, viz popis **typ nasazení** vlastnosti položky projektu služby SharePoint v [řešení vývoj služby SharePoint](../sharepoint/developing-sharepoint-solutions.md).|

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Soubory](../sharepoint/files-element.md)|Určuje soubory, které chcete zahrnout do položky projektu služby SharePoint při nasazení do služby SharePoint.|

## <a name="remarks"></a>Poznámky
 Soubory služby SharePoint, které jsou obvykle odkazované **ProjectItemFile –** prvky patří soubory funkcí – element (*Elements.xml*), soubory schémat pro seznam definic (*Schema.xml*) a soubory definic webové části pro webové části (*.webpart*).

## <a name="element-information"></a>Informace o elementu

|||
|-|-|
|**Namespace**|http:\/\/schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**Název schématu**|Schéma položky projektu služby SharePoint|
|**Soubor ověření**|ProjectItemModelSchema.xsd|
|**Může být prázdný**|Ne|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)

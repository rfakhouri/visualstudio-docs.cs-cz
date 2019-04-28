---
title: TemplateId – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateID
helpviewer_keywords:
- <TemplateID> element [Visual Studio Templates]
- TemplateID element [Visual Studio Templates]
ms.assetid: 6ca24b4e-0325-4a9e-855e-0cbbe7361d8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f1f992d9f501b965fc300b97613a3d6f3bd4e35d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62798952"
---
# <a name="templateid-element-visual-studio-templates"></a>TemplateID – element (šablony sady Visual Studio)
Určuje identifikátor pro šablony položky, která je rozdělená na skupinu šablony položek podle [templategroupid –](../extensibility/templategroupid-element-visual-studio-templates.md) elementu.

 \<Vstemplate – > \<TemplateData > \<TemplateID >

## <a name="syntax"></a>Syntaxe

```
<TemplateID> ... </TemplateID>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené elementy
 Žádné

### <a name="parent-elements"></a>Nadřazené elementy

|Prvek|Popis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.|

## <a name="text-value"></a>Textová hodnota
 A `string` , která představuje identifikátor šablony položky, která je rozdělená na skupinu šablony položek podle `TemplateGroupID` elementu.

## <a name="remarks"></a>Poznámky
 `TemplateID` je volitelný prvek.

 Pokud se vynechá soubor .vstemplate `TemplateID` elementu, pak bude [název](../extensibility/name-element-visual-studio-templates.md) element se používá jako identifikátor šablony.

 Hodnota `TemplateID` element se používá spolu s registrace systému projektu (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\Projects\\) do šablony filtrů, které se zobrazují v **přidat novou položku** Dialogové okno.

## <a name="see-also"></a>Viz také
- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
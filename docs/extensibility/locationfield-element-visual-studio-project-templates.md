---
title: Locationfield – Element (šablony projektů Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#LocationField
helpviewer_keywords:
- LocationField element [Visual Studio project templates]
ms.assetid: 6aaaa155-6ce0-4f7f-aa50-8d63d7a7c992
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b440595207cee6a146e6d85ee5e9f7c492ee3eee
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66309174"
---
# <a name="locationfield-element-visual-studio-project-templates"></a>Locationfield – element (šablony projektů Visual Studio)
Určuje, zda je či není **umístění** textové pole **nový projekt** dialogové okno je povolena, zakázané nebo skrytý pro šablonu projektu.

 \<VSTemplate> \<TemplateData> \<LocationField>

## <a name="syntax"></a>Syntaxe

```
<LocationField> Enabled/Disabled/Hidden </LocationField>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt**.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Text platné hodnoty jsou:

- `Enabled`, který určuje, že **umístění** pomocí boxingu **nový projekt** dialogové okno je povolená.

- `Disabled`, který určuje, že **umístění** pomocí boxingu **nový projekt** dialogové okno je zakázaná.

- `Hidden`, který určuje, že **umístění** pomocí boxingu **nový projekt** dialogové okno je skrytá.

## <a name="remarks"></a>Poznámky
 Výchozí hodnota je `Enabled`.

 **Umístění** textové pole **nový projekt** dialogové okno umožňuje uživatelům změnit výchozí adresář, ve kterém se uloží nové projekty.

 Hodnota zadaná v `Location` elementu je jenom respektovat dialogových oken Pokud podkladový systém projektu podporuje.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metadata [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablony.

```
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic template</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <LocationField>Disabled</LocationField>
    </TemplateData>
    <TemplateContent>
        <Project File="MyTemplate.csproj">
            <ProjectItem>Form1.cs<ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také:
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
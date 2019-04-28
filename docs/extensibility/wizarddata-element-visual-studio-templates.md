---
title: WizardData – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#WizardData
helpviewer_keywords:
- WizardData element [Visual Studio Templates]
- <WizardData> element [Visual Studio Templates]
ms.assetid: d0403a16-5d07-4fe5-b474-19ae3d9fd3ab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c6b61c62e8a3b69963bd56129fd3e7168271fc07
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62951219"
---
# <a name="wizarddata-element-visual-studio-templates"></a>WizardData – element (šablony sady Visual Studio)

Určuje vlastní kód XML

```xml
\<VSTemplate>
\<WizardData>
```

## <a name="syntax"></a>Syntaxe

```xml
<WizardData>
    <!-- XML to pass to the custom wizard extension -->
    ...
</WizardData>
```

## <a name="attributes-and-elements"></a>Atributy a elementy

Následující oddíly popisují atributy a podřízené a nadřazené elementy.

### <a name="attributes"></a>Atributy

Žádné

### <a name="child-elements"></a>Podřízené elementy

Žádné

### <a name="parent-elements"></a>Nadřazené elementy

|Prvek|Popis|
|-------------|-----------------|
|[Vstemplate –](../extensibility/vstemplate-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Obsahuje všechna metadata pro šablony projektu, šablonu položky nebo starter kit.|

## <a name="text-value"></a>Textová hodnota

Textová hodnota je volitelná.

Tento text určuje vlastní kód XML k předání do zadané v rozšíření vlastního průvodce [WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md) elementu.

## <a name="remarks"></a>Poznámky

V tomto elementu lze zadat libovolný XML. Soubor XML se předá jako parametr do rozšíření vlastního průvodce povolení rozšíření používat obsah tohoto prvku. Žádné ověření se provádí na těchto datech.

Obsah **WizardData** prvek předán, beze změny, jako parametr v řetězci slovníku parametrů v `IWizard.RunStarted` metody. Klíč slovníku jmenuje `$wizarddata$`.

## <a name="example"></a>Příklad

Následující příklad ukazuje metadata pro šablony standardní projektu pro C# aplikace Windows.

```xml
<VSTemplate Version="3.0.0" Type="Item"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyTemplate</Name>
        <Description>Template using IWizard extension</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
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
    <WizardExtension>
        <Assembly>MyWizard, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom=null</Assembly>
        <FullClassName>MyWizard.CustomWizard</FullClassName>
    </WizardExtension>
    <WizardData>
        <!-- XML to pass to the custom wizard extension -->
    </WizardData>
</VSTemplate>
```

## <a name="see-also"></a>Viz také:

- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [WizardExtension – element (šablony sady Visual Studio)](../extensibility/wizardextension-element-visual-studio-templates.md)
- [Postupy: Použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md)
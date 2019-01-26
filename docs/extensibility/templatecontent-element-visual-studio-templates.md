---
title: TemplateContent – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateContent
helpviewer_keywords:
- TemplateContent element [Visual Studio project templates]
ms.assetid: 90ae401c-b294-49ac-98da-e0d274f5bebb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c27f9ce239d5d82dc972186912266cea0d4f1ddf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55070497"
---
# <a name="templatecontent-element-visual-studio-templates"></a>TemplateContent – element (šablony sady Visual Studio)

Určuje obsah značek šablony.

Element hierarchie:

```xml
<VSTemplate>
  <TemplateContent>
```

## <a name="syntax"></a>Syntaxe

```xml
<TemplateContent>
    ...
</TemplateContent>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|[Buildonload –](../extensibility/buildonload-visual-studio-templates.md)|Určuje, jestli se má sestavit řešení, když je projekt vytvořen z šablony.|

### <a name="child-elements"></a>Podřízené elementy

|Prvek|Popis|
|-------------|-----------------|
|[ProjectCollection](../extensibility/projectcollection-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje uspořádání a obsah víceprojektových šablon.|
|[Projekt](../extensibility/project-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje soubory nebo adresáře přidat do projektu.|
|[Odkazy](../extensibility/references-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje odkazy na sestavení vyžadované pro šablonu položky.|
|[ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)|Volitelný element.<br /><br /> Určuje soubor v šabloně.|
|[CustomParameters –](../extensibility/customparameters-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje všechny vlastní parametry, které se mají použít při vytvoření projektu nebo položky z této šablony.|

### <a name="parent-elements"></a>Nadřazené elementy

|Prvek|Popis|
|-------------|-----------------|
|[Vstemplate –](../extensibility/vstemplate-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Obsahuje všechna metadata pro šablony projektu, šablonu položky nebo starter kit.|

## <a name="remarks"></a>Poznámky
 `TemplateContent` je požadovaný element.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metadata pro šablona projektu pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikace.

```xml
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic starter kit</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
    </TemplateData>
    <TemplateContent>
        <Project File="MyStarterKit.csproj">
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

- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
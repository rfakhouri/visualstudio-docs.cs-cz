---
title: Fullclassname – element (rozšíření Průvodce pro šablony VS)
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#FullClassName
helpviewer_keywords:
- FullClassName element [Visual Studio project template]
ms.assetid: 651e1010-d529-4856-85ff-c77ceca5d2ed
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 63b7e480944e8f5519db1c9cfd123c07a0cf6208
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66342632"
---
# <a name="fullclassname-element-visual-studio-template-wizard-extension"></a>Fullclassname – element (rozšíření Průvodce pro šablony sady Visual Studio)
Plně kvalifikovaný název třídy, která implementuje `IWizard` rozhraní.

 \<Vstemplate – > \<WizardExtension >... \<FullClassName>

## <a name="syntax"></a>Syntaxe

```xml
<FullClassName>ClassName</FullClassName>
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
|[WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md)|Obsahuje elementy registrace pro přizpůsobení Průvodce šablonou.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Tento text určuje třídu, která implementuje `IWizard` rozhraní. Zadaná třída musí existovat v sestavení určeném parametrem [sestavení](../extensibility/assembly-element-visual-studio-template-wizard-extension.md) elementu.

## <a name="remarks"></a>Poznámky
 `FullClassName` je vyžadovaný podřízený prvek `WizardExtension`.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metadata pro šablony standardní projektu pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikace Windows.

```
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
</VSTemplate>
```

## <a name="see-also"></a>Viz také:
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Postupy: Použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md)
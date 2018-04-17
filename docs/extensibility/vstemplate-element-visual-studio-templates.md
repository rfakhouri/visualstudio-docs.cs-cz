---
title: VSTemplate – Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#VSTemplate
helpviewer_keywords:
- VSTemplate element [Visual Studio project templates]
ms.assetid: f8ac561b-3b0b-4246-9ec9-118d2447e9a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f6151dfd852a76caa1dccbae55241af89681fd81
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vstemplate-element-visual-studio-templates"></a>VSTemplate – element (šablony sady Visual Studio)
Obsahuje všechna metadata o šablona projektu, šablony položky nebo starter kit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<VSTemplate Type="TemplateType" Version="x.x.x">  
    <TemplateData>    </TemplateData>  
    <TemplateContent>    </TemplateContent>  
    ...  
</VSTemplate>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Type`|Slouží k identifikaci šablony jako šablona projektu nebo šablony položky. Tento atribut může mít hodnotu `Project` nebo `Item`.|  
|`Version`|Určuje číslo verze pro šablonu. Šablony v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] a [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] mít `Version` hodnotu atributu `3.0.0`.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje data, která rozděluje šablony a definuje, jak se zobrazuje v **nový projekt** nebo **přidat novou položku** dialogové okno.|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje obsah šablony.|  
|[WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md)|Volitelný element.|  
|[WizardData –](../extensibility/wizarddata-element-visual-studio-templates.md)|Volitelný element.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
 Žádné  
  
## <a name="remarks"></a>Poznámky  
 `VSTemplate` Element není kořenovým elementem .vstemplate souborů.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metadata pro šablona projektu pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikace.  
  
```  
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
            <ProjectItem>Form1.cs</ProjectItem>  
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
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
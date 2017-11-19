---
title: "Project – Element (šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#Project
helpviewer_keywords:
- Project element [Visual Studio Templates]
- <Project> element [Visual Studio Templates]
ms.assetid: 1da15ea6-26e2-462b-a03e-584ef4996579
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6b4a60bdd81d2e6428d0fdafa6547227a496f862
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="project-element-visual-studio-templates"></a>Element projektu (šablony sady Visual Studio)
Určuje soubory nebo adresáře, které chcete přidat do projektu.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Projekt >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Project  
    File="MyProject.proj"  
    TargetFileName="MyTargetProject.proj"  
    ReplaceParameters="true/false">  
    IgnoreProjectParameter="$myCustomParameter$"  
        ...  
</Project>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`File`|Požadovaný atribut.<br /><br /> Určuje název souboru projektu v souboru ZIP šablony.|  
|`ReplaceParameters`|Nepovinný atribut.<br /><br /> Logická hodnota, která určuje, zda je soubor projektu hodnoty parametrů, které se musí nahradit při vytváření projektu ze šablony. Výchozí hodnota je `false`.|  
|`TargetFileName`|Nepovinný atribut.<br /><br /> Určuje název souboru projektu, když na projekt je vytvořený z šablony.|  
|`IgnoreProjectParameter`|Nepovinný atribut.<br /><br /> Určuje, zda projekt by měl být přidán k aktuálnímu řešení. Pokud hodnota parametru vlastní "$*myCustomParameter*$" existuje v souboru nahrazení parametru projektu vytvoří, ale není přidat jako součást aktuálně otevřené řešení.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Složka](../extensibility/folder-element-visual-studio-project-templates.md)|Volitelný element.<br /><br /> Určuje složku pro přidání do projektu.|  
|[ProjectItem –](../extensibility/projectitem-element-visual-studio-project-templates.md)|Volitelný element.<br /><br /> Určuje soubor, který chcete přidat do projektu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Požadovaný element.|  
  
## <a name="remarks"></a>Poznámky  
 `Project`představuje volitelný podřízený prvek `TemplateContent`.  
  
 `Project` Element se používá k zadejte projektu a proto je platná pouze v rámci šablon projektu.  
  
 `Project`může mít elementy [složky](../extensibility/folder-element-visual-studio-project-templates.md) podřízené elementy nebo [ProjectItem](../extensibility/projectitem-element-visual-studio-project-templates.md) podřízených elementů, ale není kombinaci těchto dvou možností `Folder` a `ProjectItem` podřízené elementy.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Název souboru projektu na základě zadaného uživatelem, v názvu automaticky přejmenuje **nový projekt** dialogové okno. Použití `TargetFileName` atribut, pokud chcete zadejte název souboru alternativní souborů projektu vytvořených pomocí šablony.  
  
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
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [ProjectItem – Element (šablony projektů Visual Studio)](../extensibility/projectitem-element-visual-studio-project-templates.md)   
 [Folder – Element (šablony projektů Visual Studio)](../extensibility/folder-element-visual-studio-project-templates.md)
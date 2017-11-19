---
title: "Folder – Element (šablony projektů Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#Folder
helpviewer_keywords: Folder element [Visual Studio project templates]
ms.assetid: 558e3d41-0db5-4c44-82bb-6bb87892b093
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 677b705015b2b12ee484db7595d6cfd919ad61d1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="folder-element-visual-studio-project-templates"></a>Element složky (šablony projektů sady Visual Studio)
Určuje složku, který bude přidán do projektu.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Projekt >  
 \<Složka >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Folder Name="Project Folder">  
    <Folder> ... </Folder>  
    <ProjectItem> ... </ProjectItem>  
</Folder>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadovaný atribut.<br /><br /> Název složky projektu.|  
|`TargetFolderName`|Nepovinný atribut.<br /><br /> Určuje název složky při vytváření projektu ze šablony. Tento atribut je užitečné pro vytvoření názvu složky pomocí nahrazení parametru nebo pojmenování složka s mezinárodní řetězec, který nelze použít přímo v souboru ZIP.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|`Folder`|Určuje složku pro přidání do projektu. `Folder`prvky mohou obsahovat podřízené `Folder` elementy.|  
|[ProjectItem –](../extensibility/projectitem-element-visual-studio-item-templates.md)|Určuje soubor, který chcete přidat do projektu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../extensibility/project-element-visual-studio-templates.md)|Volitelný podřízený prvek [TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md).|  
  
## <a name="remarks"></a>Poznámky  
 `Folder`je volitelné podřízeným `Project`.  
  
 Můžete použít některou z následujících metod k uspořádání položek projektu do složky v šabloně:  
  
-   Zahrnout složky soubor .zip šablony a přidat je do tohoto projektu v souboru .vstemplate zadáním cesty k souboru v `ProjectItem` elementy bez `Folder` elementy. Toto je doporučená metoda. Příklad:  
  
     `...`  
  
     `<ProjectItem>\Folder\item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   Zahrnout složky soubor .zip šablony a přidat je do tohoto projektu v souboru .vstemplate s `Folder` elementy. Příklad:  
  
     `...`  
  
     `<Folder name="Folder">`  
  
     `<ProjectItem>item.cs</ProjectItem>`  
  
     `</Folder>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   Nezahrnují složek v souboru ZIP šablony, ale přidání složek pomocí `TargetFileName` atribut `ProjectItem` elementu. Příklad:  
  
     `...`  
  
     `<ProjectItem TargetFileName="\Folder\item.cs">item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje metadata pro šablona projektu pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikací systému Windows.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <Folder Name="Properties">  
                <ProjectItem>AssemblyInfo.cs</ProjectItem>  
                <ProjectItem>Resources.resx</ProjectItem>  
                <ProjectItem>Resources.Designer.cs</ProjectItem>  
                <ProjectItem>Settings.settings</ProjectItem>  
                <ProjectItem>Settings.Designer.cs</ProjectItem>  
            </Folder>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [ProjectItem – Element (šablony sady Visual Studio položky)](../extensibility/projectitem-element-visual-studio-item-templates.md)
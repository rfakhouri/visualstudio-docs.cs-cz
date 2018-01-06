---
title: "ProjectType – Element (šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#ProjectType
helpviewer_keywords: ProjectType element [Visual Studio project templates]
ms.assetid: ccf9d83f-c7f3-49c7-a31f-e1f22bec004c
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 46f9f748f683558e6fb82607d4c87a0a0dbc1cae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="projecttype-element-visual-studio-templates"></a>ProjectType – element (šablony sady Visual Studio)
Rozděluje šablonu projektu tak, aby se v zadané skupině v **nový projekt** nebo **přidat novou položku** dialogové okno.  
  
> [!WARNING]
>  Šablony projektů jsou podporovány pro jazyk C++ spouštění v sadě Visual Studio 2012. Některé funkce nejsou podporovány pro jazyk C++ v sadě Visual Studio 2010 a starší verze.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<ProjectType – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectType> CSharp/VisualBasic/VC/Web </ProjectType>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Rozděluje šablonu a definuje, jak se zobrazuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Tato hodnota určuje typ projektu šablony vytvoří a musí obsahovat jeden z následujících hodnot:  
  
-   `CSharp`: Určuje, že šablona vytvoří [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projektu nebo položky.  
  
-   `VisualBasic`: Určuje, že šablona vytvoří [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projektu nebo položky.  
  
-   `Web`: Určuje, že šablona vytvoří webový projekt nebo položky. Pokud `ProjectType` element obsahuje tuto hodnotu, jazyk projektu nebo položky je definována v [ProjectSubType – Element (šablony sady Visual Studio)](../extensibility/projectsubtype-element-visual-studio-templates.md).  
  
## <a name="remarks"></a>Poznámky  
 `ProjectType`je požadovaný podřízený element `TemplateData`.  
  
 Hodnota `ProjectType` element určuje umístění šablony v **nový projekt** nebo **přidat novou položku** dialogové okno. Například šablonu s `ProjectType` hodnotu `CSharp` se zobrazí v části **Visual C#** uzlu **nový projekt** dialogové okno.  
  
 Podtyp šablony lze zadat pomocí [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) elementu.  
  
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
 [ProjectSubType – element (šablony sady Visual Studio)](../extensibility/projectsubtype-element-visual-studio-templates.md)
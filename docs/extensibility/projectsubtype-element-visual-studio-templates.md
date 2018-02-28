---
title: "ProjectSubType – Element (šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectSubType
helpviewer_keywords:
- ProjectSubType element [Visual Studio Templates]
- <ProjectSubType> element [Visual Studio Templates]
ms.assetid: f6895cd4-3e95-4f0e-aa9e-8c7750f46ed4
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 11effbe7e1fc6c7380ba8dbc8da3f2fe14614b5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="projectsubtype-element-visual-studio-templates"></a>ProjectSubType – element (šablony sady Visual Studio)
Klasifikuje do podkategorie z hodnoty zadané v šabloně `ProjectType` elementu.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<ProjectSubType >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectSubType> SubType </ProjectSubType>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Tato hodnota Určuje podkategorii šablony.  
  
## <a name="remarks"></a>Poznámky  
 `ProjectSubType`představuje volitelný podřízený prvek `TemplateData`.  
  
 `ProjectSubType` Element poskytuje podkategorii tak, aby [ProjectType](../extensibility/projecttype-element-visual-studio-templates.md) elementu. Tato hodnota může zahrnovat:  
  
-   `SmartDevice-NETCFv1`: Určuje, že šablona cíle [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] verze 1.0.  
  
-   `SmartDevice-NETCFv2`: Určuje, že cíle tempalate [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] verze 2.0.  
  
 Pokud obsahuje šablony `ProjectType` element s hodnotou `Web`, `ProjectSubType` element určuje programovací jazyk šablony. Tento element může mít následující hodnoty:  
  
-   `CSharp`: Určuje, že šablona vytvoří [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] webového projektu nebo položky.  
  
-   `VisualBasic`: Určuje, že šablona vytvoří [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] webového projektu nebo položky.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metadata pro šablona projektu pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] cílení aplikace zařízení [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] verze 2.0.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic device template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <ProjectSubType>SmartDevice-NETCFv2</ProjectSubType>  
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
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [ProjectType – element (šablony sady Visual Studio)](../extensibility/projecttype-element-visual-studio-templates.md)
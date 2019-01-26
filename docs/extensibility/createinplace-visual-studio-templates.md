---
title: Createinplace – element (šablony sady Visual Studio)
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CreateInPlace
helpviewer_keywords:
- CreateInPlace element [Visual Studio Templates]
- <CreateInPlace> element [Visual Studio Templates]
ms.assetid: 420d46ea-2470-4da9-ad8e-95165588a920
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8ab8c4e3ae0a217c7877d1d2e64727e45d14ea87
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069823"
---
# <a name="createinplace-element-visual-studio-templates"></a>Createinplace – element (šablony sady Visual Studio)
Určuje, jestli se má vytvořit projekt a provést nahrazení parametrů v zadaném umístění, nebo provést nahrazení parametrů v dočasném umístění a potom uložte projekt do zadaného umístění.  
  
 \<Vstemplate – >  
 \<TemplateData>  
 \<CreateInPlace>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<CreateInPlace> true/false </CreateInPlace>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené prvky  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené prvky  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Text musí být buď `true` nebo `false`. Pokud `true`, vytvoření projektu a nahrazení parametru se provádí v umístění zadaném v **nový projekt** dialogové okno. Pokud `false`, se provádí nahrazení parametru do dočasného umístění a projekt se pak zkopíruje do zadaného umístění.  
  
## <a name="remarks"></a>Poznámky  
 `CreateInPlace` je volitelný prvek. Výchozí hodnota je `true`.  
  
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
        <CreateInPlace>false</CreateInPlace>  
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
 [Vytvoření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
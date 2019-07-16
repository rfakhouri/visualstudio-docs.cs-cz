---
title: Buildprojectonload – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: b07d3074-0fc9-45e1-baf5-da6bd4f3f1c0
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 464c427008c739f23431c58bd647aaa3b1f5609d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184656"
---
# <a name="buildprojectonload-element-visual-studio-templates"></a>BuildProjectOnLoad – element (šablony sady Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Jak vytvořit a přidat je do řešení, sestavení pouze nové projekty. Celé řešení není vytvořená.  
  
 \<Vstemplate – >  
 \<TemplateData >  
 \<BuildProjectOnLoad>  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
<BuildProjectOnLoad> true/false </BuildOnLoad>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|TemplateData|Rozděluje šablonu a definuje, jak se zobrazuje v obou **nový projekt** a **přidat novou položku** dialogových oknech.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Text musí být buď `true` nebo `false` označující, jestli se má sestavení pouze nový projekt, když je vytvořen z šablony.  
  
## <a name="remarks"></a>Poznámky  
 `BuildProjectOnLoad` je volitelný prvek. Výchozí hodnota je `false`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metadata pro šablony Visual C#.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <BuildProjectOnLoad>true</BuildProjectOnLoad>  
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
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)

---
title: SolutionFolder – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SolutionFolder
helpviewer_keywords:
- <SolutionFolder> element [Visual Studio Templates]
- SolutionFolder element [Visual Studio Templates]
ms.assetid: 963f0398-fb50-4d8e-879d-d48f8b7c6d80
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 84d0c1765a14f60363b71fcdec182d448cb4f112
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68205546"
---
# <a name="solutionfolder-element-visual-studio-templates"></a>SolutionFolder – element (šablony sady Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Seskupuje projekty do víceprojektových šablon.  
  
 \<Vstemplate – >  
 \<TemplateContent>  
 \<Projectcollection – >  
 \<SolutionFolder>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<SolutionFolder Name="DirectoryName">  
    ...  
</SolutionFolder>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadovaný atribut.<br /><br /> Název složky řešení.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectTemplateLink –](../extensibility/projecttemplatelink-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje cestu k souboru .vstemplate jednoho projektu ve víceprojektové šabloně.|  
|`SolutionFolder`|Volitelný element.<br /><br /> Seskupuje projekty do víceprojektových šablon.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ProjectCollection](../extensibility/projectcollection-element-visual-studio-templates.md)|Určuje uspořádání a obsah víceprojektových šablon.|  
|`SolutionFolder`|Seskupuje projekty do víceprojektových šablon.|  
  
## <a name="remarks"></a>Poznámky  
 Šablony vícenásobných projektů slouží jako kontejnery pro dva nebo více projektů. `SolutionFolder` Element slouží k uspořádání projektů v šabloně do skupin. Složky určené `SolutionFolder` prvky jsou vytvořeny jako složky řešení v projektu v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Další informace o víceprojektových šablonách naleznete v tématu [jak: Vytváření šablon vícenásobného projektu](../ide/how-to-create-multi-project-templates.md).  
  
## <a name="example"></a>Příklad  
 V tomto příkladu `SolutionFolder` elementu a rozdělit do dvou skupin víceprojektové šabloně `Math Classes` a `Graphics Classes`. Šablona obsahuje čtyři projekty, z nichž dva jsou umístěny ve složce jednotlivých řešení.  
  
```  
<VSTemplate Version="3.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <SolutionFolder Name="Math Classes">  
                <ProjectTemplateLink ProjectName="MathClassLib1">  
                    MathClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="MathClassLib2">  
                    MathClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
            <SolutionFolder Name="Graphics Classes">  
                <ProjectTemplateLink ProjectName="GraphicsClassLib1">  
                    GraphicsClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="GraphicsClassLib2">  
                    GraphicsClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Postupy: Vytváření šablon vícenásobného projektu](../ide/how-to-create-multi-project-templates.md)

---
title: "ProjectTemplateLink – Element (šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#ProjectTemplateLink
helpviewer_keywords:
- <ProjectTemplateLink> element [Visual Studio Templates]
- ProjectTemplateLink element [Visual Studio Templates]
ms.assetid: b0449111-8b48-45a1-a031-ea24b765e969
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9e614b2ec8ef404ef21e665ac5ae26dd73253f55
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="projecttemplatelink-element-visual-studio-templates"></a>ProjectTemplateLink – element (šablony sady Visual Studio)
Určuje cestu k souboru .vstemplate jednoho projektu ve víceprojektové šabloně.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Projectcollection – >  
 \<ProjectTemplateLink >  
-nebo-  
\<VSTemplate >  
 \<TemplateContent >  
 \<Projectcollection – >  
 \<SolutionFolder >  
 \<ProjectTemplateLink >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectTemplateLink ProjectName="Name">  
    PathToTemplateFile  
</ProjectTemplateLink>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`ProjectName`|Nepovinný atribut.<br /><br /> Určuje název pro každý projekt ve víceprojektové šabloně. **Nový projekt** dialogové okno nelze přiřadit názvy do jednotlivých projektů.|  
|`CopyParameters`|Umožňuje zkopírovat všechny proměnné z hlavní šablony skupiny do jednotlivých propojených šablon.<br /><br /> Parametry v propojených šablon mít předponu `"$ext_*$"`. Například pokud v šabloně nadřazené skupiny parametr `$projectname$` má hodnotu **ExampleProject1**, když propojené šablony získá jeho zapnout mají být provedeny, získá parametr `$ext_projectname$`, což je kopie `$projectname$`parametr ze šablony nadřazené skupiny.<br /><br /> To umožňuje propojeným šablonám sdílet určité společné parametry, které stačí jednoduše vytvořit pouze v nadřazené šabloně skupiny.<br /><br /> Tento atribut je volitelná a bude automaticky výchozí `false` při není zahrnutý.<br /><br /> Dostupné ve verzi Visual Studio 2013 Update 2. Chcete-li verze produktu správný, najdete v části [odkazování na sestavení poskytnuté ve Visual Studio 2013 SDK Update 2](http://msdn.microsoft.com/en-us/42b65c3e-e42b-4c39-98c8-bea285f25ffb).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Projectcollection –](../extensibility/projectcollection-element-visual-studio-templates.md)|Určuje uspořádání a obsah víceprojektových šablon.|  
|[SolutionFolder](../extensibility/solutionfolder-element-visual-studio-templates.md)|Seskupuje projekty do víceprojektových šablon.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Tento text určuje cestu k souboru .vstemplate šablony.  
  
## <a name="remarks"></a>Poznámky  
 Šablony vícenásobných projektů slouží jako kontejnery pro dva nebo více projektů. `ProjectTemplateLink` Element se používá k určení umístění souboru .vstemplate pro jeden z projektů v šabloně. Soubor .vstemplate šablony vícenásobného projektu obsahuje jeden `ProjectTemplateLink` element pro každý projekt v šabloně. Další informace o víceprojektových šablon najdete v tématu [postupy: vytváření šablon vícenásobného projektu](../ide/how-to-create-multi-project-templates.md).  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje jednoduchý kořenový soubor .vstemplate víceprojektové šablony, V tomto příkladu šablona obsahuje dva projekty `My Windows Application` a `My Class Library`. `ProjectName` Atributu u `ProjectTemplateLink` element nastaví název pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] k přiřazení tohoto projektu. Pokud `ProjectName` atribut neexistuje, název souboru .vstemplate slouží jako název projektu.  
  
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
            <ProjectTemplateLink ProjectName="My Windows Application">  
                WindowsApp\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
            <ProjectTemplateLink ProjectName="My Class Library" CopyParameters="true">  
                ClassLib\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Postupy: Vytváření šablon vícenásobného projektu](../ide/how-to-create-multi-project-templates.md)
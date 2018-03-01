---
title: "Locationfield – Element (šablony projektů Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#LocationField
helpviewer_keywords:
- LocationField element [Visual Studio project templates]
ms.assetid: 6aaaa155-6ce0-4f7f-aa50-8d63d7a7c992
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1aa4acf4b0d2aeb83e4ea4feb70ace3ae55ea2b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="locationfield-element-visual-studio-project-templates"></a>LocationField – element (šablony projektů Visual Studio)
Určuje, jestli **umístění** textového pole **nový projekt** dialogové okno je povoleno, zakázán nebo skryto šablona projektu.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<Locationfield – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<LocationField> Enabled/Disabled/Hidden </LocationField>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje v buď **nový projekt**.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Text platné hodnoty jsou:  
  
-   `Enabled`, která určuje, že **umístění** pole **nový projekt** dialogové okno je povoleno.  
  
-   `Disabled`, která určuje, že **umístění** pole **nový projekt** dialogové okno je zakázána.  
  
-   `Hidden`, která určuje, že **umístění** pole **nový projekt** dialogové okno je skrytá.  
  
## <a name="remarks"></a>Poznámky  
 Výchozí hodnota je `Enabled`.  
  
 **Umístění** textového pole **nový projekt** dialogové okno umožňuje uživatelům změnit výchozí adresář, ve kterém jsou uloženy nové projekty.  
  
 Hodnota zadaná v `Location` element je pouze berou v úvahu dialogové okno pokud ji podporuje základní systému projektu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje metadata pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablony.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <LocationField>Disabled</LocationField>  
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
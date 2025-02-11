---
title: Locationfield – Element (šablony projektů Visual Studio) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#LocationField
helpviewer_keywords:
- LocationField element [Visual Studio project templates]
ms.assetid: 6aaaa155-6ce0-4f7f-aa50-8d63d7a7c992
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b28fe0e696b23724758bd877b6031287290f879e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194464"
---
# <a name="locationfield-element-visual-studio-project-templates"></a>LocationField – element (šablony projektů Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje, zda je či není **umístění** textové pole **nový projekt** dialogové okno je povolena, zakázané nebo skrytý pro šablonu projektu.  
  
 \<Vstemplate – >  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt**.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Text platné hodnoty jsou:  
  
- `Enabled`, který určuje, že **umístění** pomocí boxingu **nový projekt** dialogové okno je povolená.  
  
- `Disabled`, který určuje, že **umístění** pomocí boxingu **nový projekt** dialogové okno je zakázaná.  
  
- `Hidden`, který určuje, že **umístění** pomocí boxingu **nový projekt** dialogové okno je skrytá.  
  
## <a name="remarks"></a>Poznámky  
 Výchozí hodnota je `Enabled`.  
  
 **Umístění** textové pole **nový projekt** dialogové okno umožňuje uživatelům změnit výchozí adresář, ve kterém se uloží nové projekty.  
  
 Hodnota zadaná v `Location` elementu je jenom respektovat dialogových oken Pokud podkladový systém projektu podporuje.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metadata [!INCLUDE[csprcs](../includes/csprcs-md.md)] šablony.  
  
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

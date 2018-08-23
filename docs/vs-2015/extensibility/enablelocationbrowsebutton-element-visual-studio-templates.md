---
title: Enablelocationbrowsebutton – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#EnableLocationBrowseButton
helpviewer_keywords:
- EnableLocationBrowseButton [Visual Studio project templates]
ms.assetid: a12d10d8-af49-482a-af77-e084fd07a47d
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ee375914a732c61053d505e098cd1f5b7a6e0c48
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667804"
---
# <a name="enablelocationbrowsebutton-element-visual-studio-templates"></a>EnableLocationBrowseButton – element (šablony sady Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [enablelocationbrowsebutton – Element (šablony sady Visual Studio)](https://docs.microsoft.com/visualstudio/extensibility/enablelocationbrowsebutton-element-visual-studio-templates).  
  
Určuje, zda **Procházet** tlačítko je k dispozici v **nový projekt** dialogovém okně tak, aby uživatelé mohli snadno upravovat výchozí adresář, ve kterém je uložený nový projekt.  
  
 \<Vstemplate – >  
 \<TemplateData >  
 \<Enablelocationbrowsebutton – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<EnableLocationBrowseButton> true/false </EnableLocationBrowseButton>  
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
|[TemplateData –](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Text musí být buď `true` nebo `false`, označující, jestli se mají zobrazit **Procházet** tlačítko **nový projekt** dialogové okno.  
  
## <a name="remarks"></a>Poznámky  
 `EnableLocationBrowseButton` je volitelný prvek. Výchozí hodnota je `true`, které ukazuje **Procházet** tlačítko **nový projekt** dialogové okno.  
  
 V **nový projekt** dialogové okno, **umístění** textového pole určuje adresář, ve kterém je uložený nový projekt. **Procházet** tlačítko umožňuje upravit tento adresář zobrazením **umístění projektu** dialogové okno, které umožňuje snadno přejít do jiného adresáře, který je dostupný z vašeho počítače, a vyberte ji jako adresář, ve kterém je uložený nový projekt.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metadata [!INCLUDE[csprcs](../includes/csprcs-md.md)] aplikace Windows.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <EnableLocationBrowseButton>false</EnableLocationBrowseButton>  
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


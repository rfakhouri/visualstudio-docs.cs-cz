---
title: TemplateData – Element (šablony sady Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateData
helpviewer_keywords:
- TemplateData element [Visual Studio project templates]
ms.assetid: db17ec9b-bfdf-46b1-bbe7-5ccc140056e2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bbf5b4c26b46c0be6038651a41c751afc39e4da5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="templatedata-element-visual-studio-templates"></a>TemplateData – element (šablony sady Visual Studio)
Rozděluje šablonu a definuje, jak se zobrazuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.  
  
 \<VSTemplate >  
 \<TemplateData >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<TemplateData>  
    <Name> ... </Name>  
    <Description> ... </Description>  
    <Icon> ... </Icon>  
    <ProjectType> ... </ProjectType>  
    ...  
</TemplateData>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Jméno](../extensibility/name-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje název šablony, jak se objevuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.|  
|[Popis](../extensibility/description-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje popis šablony, jak se objevuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.|  
|[Ikona](../extensibility/icon-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje cestu a název souboru bitové kopie, který slouží jako ikonu, která se zobrazí v některém **nový projekt** nebo **přidat novou položku** dialogové okno, šablony.|  
|[ProjectType –](../extensibility/projecttype-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu projektu tak, aby se v zadané skupině v **nový projekt** dialogové okno.|  
|[ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Klasifikuje v šabloně projektů tak, aby se v rámci zadaného podkategorii v **nový projekt** dialogové okno.|  
|[TemplateID](../extensibility/templateid-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje ID šablony.|  
|[Templategroupid –](../extensibility/templategroupid-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje ID šablony skupiny.|  
|[SortOrder –](../extensibility/sortorder-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje hodnotu, která se používá k uspořádání šablony mezi další šablony ve stejné kategorii, jak se objevuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.|  
|[Createnewfolder –](../extensibility/createnewfolder-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje, jestli se má příslušnou složku vytvořit při vytváření instance projektu.|  
|[Defaultname –](../extensibility/defaultname-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje název, který bude generovat systému projektu sady Visual Studio pro projekt nebo položku při jeho vytvoření.|  
|[Providedefaultname –](../extensibility/providedefaultname-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje, zda systém projektu sady Visual Studio vygeneruje výchozí název pro projekt nebo položku při jeho vytvoření.|  
|[PromptForSaveOnCreation](../extensibility/promptforsaveoncreation-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje, jestli se dá vytvořit projekt jako dočasné projektu.|  
|[EnableLocationBrowseButton](../extensibility/enablelocationbrowsebutton-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje, zda **Procházet** tlačítko je k dispozici v **nový projekt** dialogovém tak, aby uživatelé mohli snadno upravovat výchozí adresář, kde je uložena nový projekt.|  
|[Skryté](../extensibility/hidden-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje, zda se šablony zobrazí buď **nový projekt** nebo **přidat novou položku** dialogové okno.|  
|[NumberOfParentCategoriesToRollUp](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje počet nadřazené kategorie, které se zobrazí šablony **nový projekt** dialogové okno.|  
|[Locationfieldmruprefix –](../extensibility/locationfieldmruprefix-element-visual-studio-templates.md)|Volitelný element.|  
|[Locationfield –](../extensibility/locationfield-element-visual-studio-project-templates.md)|Volitelný element.<br /><br /> Určuje, jestli **umístění** textového pole **nový projekt** dialogové okno je povoleno, zakázána nebo skryto šablona projektu.|  
|[RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Tento element použijte, pokud šablona podporuje pouze na konkrétní minimální verzi a novější verze, pokud existuje, rozhraní .NET Framework.|  
|[Supportsmasterpage –](../extensibility/supportsmasterpage-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje, zda šablona podporuje stránku předlohy pro webové projekty.|  
|[Supportscodeseparation –](../extensibility/supportscodeseparation-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje, jestli podporuje šablony oddělení kódu nebo model kódu stránky pro webové projekty.|  
|[Supportslanguagedropdown –](../extensibility/supportslanguagedropdown-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje, zda šablona se shoduje více jazyků a zda **jazyk** možnost je dostupná z **nový projekt** dialogové okno.|  
|[Targetplatformname –](../extensibility/targetplatformname-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje platformu, která šablona cíle projektu. Tento element určuje, že šablona projektu se používá k vytvoření [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Obsahuje všechna metadata pro šablony projektu, šablony položky nebo starter kit.|  
  
## <a name="remarks"></a>Poznámky  
 `TemplateData` je požadovaný element.  
  
 Pokud Volitelný element neuvedete, je použita výchozí hodnota pro daný element.  
  
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
---
title: TemplateData – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateData
helpviewer_keywords:
- TemplateData element [Visual Studio project templates]
ms.assetid: db17ec9b-bfdf-46b1-bbe7-5ccc140056e2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f9647330aaca2c2ae91aa7e461da17cf4dc3f8c3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66316677"
---
# <a name="templatedata-element-visual-studio-templates"></a>TemplateData – element (šablony sady Visual Studio)
Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.

 \<Vstemplate – > \<TemplateData >

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

| Prvek | Popis |
| - | - |
| [Název](../extensibility/name-element-visual-studio-templates.md) | Požadovaný element.<br /><br /> Určuje název šablony, protože se zobrazí buď **nový projekt** nebo **přidat novou položku** dialogové okno. |
| [Popis](../extensibility/description-element-visual-studio-templates.md) | Požadovaný element.<br /><br /> Určuje popis šablony, protože se zobrazí buď **nový projekt** nebo **přidat novou položku** dialogové okno. |
| [Ikona](../extensibility/icon-element-visual-studio-templates.md) | Požadovaný element.<br /><br /> Určuje cestu a název souboru, který slouží jako ikona, která se zobrazí v jednom souboru obrázku **nový projekt** nebo **přidat novou položku** dialogovém okně pro šablonu. |
| [ProjectType](../extensibility/projecttype-element-visual-studio-templates.md) | Požadovaný element.<br /><br /> Rozděluje šablonu projektu tak, aby se objevila pod zadané skupiny v rámci **nový projekt** dialogové okno. |
| [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Klasifikuje šablona projektu tak, aby se objevila pod zadanou podkategorie v **nový projekt** dialogové okno. |
| [TemplateId –](../extensibility/templateid-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje ID šablony. |
| [TemplateGroupID](../extensibility/templategroupid-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje ID šablony skupiny. |
| [SortOrder](../extensibility/sortorder-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje hodnotu, která slouží k uspořádání šablony, mezi další šablony ve stejné kategorii, jak se zobrazí v buď **nový projekt** nebo **přidat novou položku** dialogové okno. |
| [CreateNewFolder](../extensibility/createnewfolder-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje, zda nadřazené složky se vytvoří při vytváření instance projektu. |
| [Defaultname –](../extensibility/defaultname-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje název, který vygeneruje systém projektu sady Visual Studio pro projekt nebo položku při jeho vytvoření. |
| [Providedefaultname –](../extensibility/providedefaultname-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje, zda systém projektu sady Visual Studio vygeneruje výchozí název pro projekt nebo položku při jeho vytvoření. |
| [PromptForSaveOnCreation](../extensibility/promptforsaveoncreation-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje, zda projekt můžete vytvořit podobě dočasného projektu (Visual Studio 2017 pouze). |
| [EnableLocationBrowseButton](../extensibility/enablelocationbrowsebutton-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje, zda **Procházet** tlačítko je k dispozici v **nový projekt** dialogovém okně tak, aby uživatelé mohli snadno upravovat výchozí adresář, ve kterém je uložený nový projekt. |
| [Hidden](../extensibility/hidden-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje, jestli se šablona zobrazuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno. |
| [NumberOfParentCategoriesToRollUp](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje počet nadřazených kategoriích, které se zobrazí v šabloně **nový projekt** dialogové okno. |
| [LocationFieldMRUPrefix](../extensibility/locationfieldmruprefix-element-visual-studio-templates.md) | Volitelný element. |
| [LocationField](../extensibility/locationfield-element-visual-studio-project-templates.md) | Volitelný element.<br /><br /> Určuje, zda je či není **umístění** textové pole **nový projekt** dialogové okno je povoleno, zakázané nebo skrytý pro šablonu projektu. |
| [RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Pomocí tohoto prvku, pokud šablony podporuje pouze konkrétní minimální verzi a novější verze, pokud je libovolná z rozhraní .NET Framework. |
| [SupportsMasterPage](../extensibility/supportsmasterpage-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje, zda šablona podporuje stránku předlohy pro webové projekty. |
| [SupportsCodeSeparation](../extensibility/supportscodeseparation-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje, jestli podporuje šablony oddělení kódu nebo použití modelu code-behind model stránky, pro webové projekty. |
| [SupportsLanguageDropDown](../extensibility/supportslanguagedropdown-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje, jestli je stejný jako pro řadu jazyků šablony a zda **jazyk** možnost je k dispozici **nový projekt** dialogové okno. |
| [TargetPlatformName](../extensibility/targetplatformname-element-visual-studio-templates.md) | Volitelný element.<br /><br /> Určuje platformu, která šablona cíle projektu. Tento prvek určuje, že šablona projektu slouží k vytvoření [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace. |

### <a name="parent-elements"></a>Nadřazené elementy

|Prvek|Popis|
|-------------|-----------------|
|[Vstemplate –](../extensibility/vstemplate-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Obsahuje všechna metadata pro šablony projektu, šablonu položky nebo starter kit.|

## <a name="remarks"></a>Poznámky
 `TemplateData` je požadovaný element.

 Pokud Volitelný element není zadána, je použita výchozí hodnota pro daný element.

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
- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
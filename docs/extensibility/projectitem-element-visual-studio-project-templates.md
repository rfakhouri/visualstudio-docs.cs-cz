---
title: ProjectItem – Element (šablony projektů Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- ProjectItem element [Visual Studio project templates]
- <ProjectItem> element [Visual Studio project templates]
ms.assetid: 82879fbe-7756-42cd-9a07-c10edf5b4673
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 09f062575cc7d0978fbacede32cfe22d0f98a71c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66335953"
---
# <a name="projectitem-element-visual-studio-project-templates"></a>ProjectItem – element (šablony projektů Visual Studio)
Určuje soubor, který je součástí šablony projektu.

> [!NOTE]
> `ProjectItem` Element přijímá různé atributy v závislosti na tom, jestli je šablona pro projekt nebo položku. Toto téma vysvětluje, `ProjectItem` – element pro šablony projektů. Pro vysvětlení, `ProjectItem` – element pro šablony položek, naleznete v tématu [ProjectItem – Element (šablony položek aplikace Visual Studio)](../extensibility/projectitem-element-visual-studio-item-templates.md).

 \<VSTemplate> \<TemplateContent> \<Project> \<ProjectItem>

## <a name="syntax"></a>Syntaxe

```
<ProjectItem
    TargetFileName="TargetFileName.ext"
    ReplaceParameters="true/false"
    OpenInEditor="true/false"
    OpenInWebBrowser="true/false"
    OpenInHelpBrowser="true/false"
    OpenOrder="Value">
        FileName.ext
</ProjectItem>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.

### <a name="attributes"></a>Atributy

| Atribut | Popis |
|---------------------| - |
| `TargetFileName` | Nepovinný atribut.<br /><br /> Určuje název a cesta k položce projektu, když je projekt vytvořen z šablony. Tento atribut je užitečné pro vytvoření adresářové struktury liší od adresářovou strukturu v šabloně *ZIP* souboru, nebo k vytvoření názvu položky pomocí nahrazení parametru. |
| `ReplaceParameters` | Nepovinný atribut.<br /><br /> Logická hodnota určující, zda položka má hodnoty parametrů, které musí být nahrazen, když je projekt vytvořen z šablony. Výchozí hodnota je `false`. |
| `OpenInEditor` | Nepovinný atribut.<br /><br /> Logická hodnota, která určuje, zda položka by měl být otevřen v jeho příslušných editoru v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] při vytvoření projektu ze šablony.<br /><br /> `OpenInWebBrowser` a `OpenInHelpBrowser` atributy se ignorují u položky s `OpenInEditor` hodnotu `true`.<br /><br /> Výchozí hodnota je `false`. |
| `OpenInWebBrowser` | Nepovinný atribut.<br /><br /> Logická hodnota, která určuje, zda položky by měla otevřít webový prohlížeč při vytvoření projektu ze šablony.<br /><br /> Pouze soubory HTML a textové soubory, které jsou místní pro projekt lze otevřít ve webovém prohlížeči. Externí adresy URL nelze otevřít pomocí tohoto atributu.<br /><br /> Výchozí hodnota je `false`. |
| `OpenInHelpBrowser` | Nepovinný atribut.<br /><br /> Logická hodnota, která určuje, zda položka by měl být otevřen v aplikaci Help viewer, když je projekt vytvořen z šablony.<br /><br /> Pouze soubory HTML a textové soubory, které jsou místní pro projekt lze otevřít v prohlížeči. Externí adresy URL nelze otevřít pomocí tohoto atributu.<br /><br /> Výchozí hodnota je `false`. |
| `OpenOrder` | Nepovinný atribut.<br /><br /> Určuje číselnou hodnotu, která představuje pořadí, položky se otevřou v jejich příslušných editorech. Všechny hodnoty musí být násobky 10. Položky s vyšší `OpenOrder` hodnoty jsou otevřen jako první. |

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Projekt](../extensibility/project-element-visual-studio-templates.md)|Určuje soubory nebo adresáře přidat do projektu.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 A `string` , která představuje název nebo cesta k souboru v šabloně *ZIP* souboru.

## <a name="remarks"></a>Poznámky
 `ProjectItem` je volitelný podřízený `Project`.

 `TargetFileName` Atribut lze použít k vytvoření adresářové struktury liší od adresářovou strukturu v šabloně *ZIP* souboru. Například pokud soubor *MyFile.vb* existuje v kořenovém adresáři šablony *ZIP* souboru, ale chcete mít soubor, který má být umístěn v adresáři s názvem *CustomFiles* ve všech projektech vytvořené z této šablony, měli byste použít následující kód XML:

```xml
<ProjectItem TargetFileName="CustomFiles\MyFile.vb">MyFile.vb</ProjectItem>
```

 `TargetFileName` Atribut lze také přejmenovat soubory, které obsahují mezinárodní znaky v jejich názvy souborů. Například šablona *ZIP* souboru nemůže obsahovat názvy souborů se znaky Unicode, takže ho musí přejmenovat, předtím, než mohou být zkomprimovány do *ZIP* souboru. `TargetFileName` Atribut je možné nastavit název souboru zpět na původní název souboru ve formátu Unicode.

 `TargetFileName` Atribut lze použít také k přejmenování souborů s parametry. Následující postup vysvětluje, jak přejmenovat soubor *MyFile.vb*, která existuje v kořenovém adresáři šablony *ZIP* soubor s názvem souboru na základě názvu projektu.

### <a name="to-rename-files-with-parameters"></a>Přejmenujte soubory s parametry

1. Použijte následující kód XML v *.vstemplate* souboru:

   ```xml
   <ProjectItem TargetFileName="$safeprojectname$.vb">MyFile.vb</ProjectItem>
   ```

2. Otevřete soubor projektu ( *.vbproj* pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projektu) v textovém editoru nebo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

3. Vyhledejte řádek v souboru projektu, který vypadá podobně jako následující kód XML:

   ```xml
   <Compile Include="MyFile.vb">
   ```

4. Řádek kódu nahraďte následující kód XML:

   ```xml
   <Compile Include="$safeprojectname$.vb">
   ```

    Pokud je projekt je vytvořen z této šablony, názvu souboru bude vycházet zadaný název uživatele v **nový projekt** dialogovém okně se všemi problematické znaky a byly odebrány mezery. Další informace najdete v tématu [parametry šablony](../ide/template-parameters.md).

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
            <ProjectItem ReplaceParameters="true">Form1.cs<ProjectItem>
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
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Parametry šablony](../ide/template-parameters.md)
- [ProjectItem – element (šablony sady Visual Studio položky)](../extensibility/projectitem-element-visual-studio-item-templates.md)
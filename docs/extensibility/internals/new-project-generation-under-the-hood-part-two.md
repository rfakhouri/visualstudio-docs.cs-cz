---
title: 'Nová generace projektů: Pod pokličkou, část 2 | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 73ce91d8-0ab1-4a1f-bf12-4d3c49c01e13
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5ccdd4cd8bafc4bc4a899ea47d62ec10e578569c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62909320"
---
# <a name="new-project-generation-under-the-hood-part-two"></a>Nová generace projektů: Pod kapotou, část 2

V [nová generace projektů: Pod pokličkou, část jednoho](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) jsme viděli jak **nový projekt** pole se vyplní dialogového okna. Předpokládejme, že jste vybrali **aplikace Visual C# Windows**, vyplněné **název** a **umístění** textová pole a kliknutí na OK.

## <a name="generating-the-solution-files"></a>Generují se soubory řešení
 Výběr šablony aplikace přesměruje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] se rozzipují a otevřou odpovídající soubor .vstemplate a spusťte šablonu a interpretovat příkazy XML v tomto souboru. Tyto příkazy vytvoří projekty a položky projektu v rámci nového nebo existujícího řešení.

 Šablona rozbalí zdrojové soubory, volá se, šablony položek ze stejné složky ZIP, který obsahuje soubor .vstemplate. Šablona zkopíruje tyto soubory do nového projektu přizpůsobení je odpovídajícím způsobem.

### <a name="template-parameter-replacement"></a>Nahrazení parametru šablony
 Když šablona zkopíruje do nového projektu šablony položky, nahradí řetězce pro přizpůsobení souboru žádné parametry šablony. Parametr šablony je speciální token, který je před a za nímž následuje znak dolaru, třeba $date$.

 Podívejme se na šablonu položky obvyklou pro projekty. Extrahovat a prozkoumejte Program.cs ve složce Program Files\Microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip.

```csharp
using System;
using System.Collections.Generic;
using System.Windows.Forms;

namespace $safeprojectname$
{
    static class Program
    {
        // source code deleted here for brevity
    }
}
```

Pokud vytvoříte nový projekt aplikace Windows s názvem jednoduchý, nahradí šablony `$safeprojectname$` parametr s názvem projektu.

```csharp
using System;
using System.Collections.Generic;
using System.Windows.Forms;

namespace Simple
{
    static class Program
    {
        // source code deleted here for brevity
    }
}
```

 Úplný seznam parametrů šablony, najdete v části [parametry šablony](../../ide/template-parameters.md).

## <a name="a-look-inside-a-vstemplate-file"></a>Podívejte se uvnitř. Soubor VSTemplate
 Soubor basic .vstemplate má tento formát

```xml
<VSTemplate Version="2.0.0"     xmlns="http://schemas.microsoft.com/developer/vstemplate/2005"     Type="Project">
    <TemplateData>
    </TemplateData>
    <TemplateContent>
    </TemplateContent>
</VSTemplate>
```

 Zvažovali jsme i \<TemplateData > v oddílu [nová generace projektů: Pod pokličkou, část 1](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md). Značky v této části se používají k řízení vzhledu **nový projekt** dialogové okno.

 Značky v \<TemplateContent > části ovládacího prvku generování nových projektů a položek projektů. Tady je \<TemplateContent > části cswindowsapplication.vstemplate souboru ve složce 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip \Program Files\Microsoft Visual Studio.

```xml
<TemplateContent>
  <Project File="WindowsApplication.csproj" ReplaceParameters="true">
    <ProjectItem ReplaceParameters="true"
      TargetFileName="Properties\AssemblyInfo.cs">
      AssemblyInfo.cs
    </ProjectItem>
    <ProjectItem TargetFileName="Properties\Resources.resx">
      Resources.resx
    </ProjectItem>
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Resources.Designer.cs">
      Resources.Designer.cs
    </ProjectItem>
    <ProjectItem TargetFileName="Properties\Settings.settings">
      Settings.settings
    </ProjectItem>
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Settings.Designer.cs">
      Settings.Designer.cs
    </ProjectItem>
    <ProjectItem ReplaceParameters="true" OpenInEditor="true">
      Form1.cs
    </ProjectItem>
    <ProjectItem ReplaceParameters="true">
      Form1.Designer.cs
    </ProjectItem>
    <ProjectItem ReplaceParameters="true">
      Program.cs
    </ProjectItem>
  </Project>
</TemplateContent>
```

 \<Projekt > značky určuje generování projektu a \<ProjectItem > značky určuje generování položky projektu. Pokud má parametr ReplaceParameters hodnotu true, šablona přizpůsobovat všech parametrů šablony v souboru projektu nebo položky. V takovém případě všechny položky projektu jsou přizpůsobené, s výjimkou Settings.settings.

 TargetFileName parametr určuje název a relativní cestu z výsledného souboru projektu nebo položky. To vám umožní vytvořit strukturu složek pro váš projekt. Pokud nezadáte tento argument, položky projektu bude mít stejný název jako šablonu položky projektu.

 Výsledný struktury složek Windows aplikace vypadá takto:

 ![SimpleSolution](../../extensibility/internals/media/simplesolution.png "SimpleSolution")

 První a jediný \<Projekt > značky v šabloně čtení:

```xml
<Project File="WindowsApplication.csproj" ReplaceParameters="true">
```

 Toto dá pokyn šabloně nový projekt pro vytvoření souboru projektu Simple.csproj zkopírováním a přizpůsobení windowsapplication.csproj šablony položky.

### <a name="designers-and-references"></a>Návrháři a odkazy
 Zobrazí se v Průzkumníku řešení, že je k dispozici vlastnosti složky a obsahuje očekávané soubory. Ale co o projekt odkazuje na a soubor návrháře závislosti, jako je například Resources.Designer.cs k Resources.resx a Form1.Designer.cs k Form1.cs?  Tato nastavení jsou v souboru Simple.csproj kdy se generují.

 Tady je \<ItemGroup > z Simple.csproj, který vytváří odkazy projektu:

```xml
<ItemGroup>
    <Reference Include="System" />
    <Reference Include="System.Data" />
    <Reference Include="System.Deployment" />
    <Reference Include="System.Drawing" />
    <Reference Include="System.Windows.Forms" />
    <Reference Include="System.Xml" />
</ItemGroup>
```

 Uvidíte, že jde o šesti projektu odkazy, které se zobrazí v Průzkumníku řešení. Tady je oddíl z jiné \<ItemGroup >. Pro přehlednost se odstranily spousty řádků kódu. Tato část umožňuje Settings.Designer.cs závisí na Settings.settings:

```xml
<ItemGroup>
    <Compile Include="Properties\Settings.Designer.cs">
        <DependentUpon>Settings.settings</DependentUpon>
    </Compile>
</ItemGroup>
```

## <a name="see-also"></a>Viz také:

- [Nová generace projektů: Pod kapotou, část 1](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)
- [MSBuild](../../msbuild/msbuild.md)
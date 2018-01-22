---
title: "Nové generace projektu: Pod pokličkou, součástí dva | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 73ce91d8-0ab1-4a1f-bf12-4d3c49c01e13
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a35010af9ee0b0d7ad885f607b8fc1e2d54a19ba
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="new-project-generation-under-the-hood-part-two"></a>Nové generace projektu: Pod pokličkou, část 2
V [nové generace projektu: pod pokličkou, jednu část](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) jsme viděli jak **nový projekt** dialogu zadá. Předpokládejme, jste vybrali **aplikaci Visual C# Windows**, vyplněné **název** a **umístění** textová pole a kliknutelnou OK.  
  
## <a name="generating-the-solution-files"></a>Generování souborů řešení  
 Výběr šablony aplikace přesměruje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] rozbalte a otevřete odpovídající soubor .vstemplate a spusťte šablonu interpretovat příkazy XML, který v tomto souboru. Tyto příkazy vytváření projektů a položek projektu do nové nebo existující řešení.  
  
 Šablona rozbalí zdrojové soubory, názvem šablony položek ze stejné složky ZIP, který obsahuje soubor .vstemplate. Šablona zkopíruje tyto soubory do nového projektu, přizpůsobení je odpovídajícím způsobem.  
  
### <a name="template-parameter-replacement"></a>Nahrazení parametru šablony  
 Pokud šablona zkopíruje na nový projekt šablony položky, nahradí všechny parametry šablony řetězce pro přizpůsobení souboru. Parametr šablony je speciální token, který je a následnou dolaru, například, $date$.  
  
 Podívejme se na šablonu položky typické projektu. Extrahování a prozkoumat Program.cs ve složce Program Files\Microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip.  
  
```  
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
  
```  
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
  
## <a name="a-look-inside-a-vstemplate-file"></a>Podívejte se uvnitř. VSTemplate souboru  
 Základní .vstemplate soubor má tento formát  
  
```  
<VSTemplate Version="2.0.0"     xmlns="http://schemas.microsoft.com/developer/vstemplate/2005"     Type="Project">  
    <TemplateData>  
    </TemplateData>  
    <TemplateContent>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 Jsme se podívali na \<TemplateData > tématu [nové generace projektu: pod pokličkou, jednu část](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md). Značky v této části je možné určit vzhled **nový projekt** dialogové okno.  
  
 Značky v \<TemplateContent > část řízení generování nových projektů a položek projektů. Tady je \<TemplateContent > části ze souboru cswindowsapplication.vstemplate ve složce 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip \Program Files\Microsoft Visual Studio.  
  
```  
<TemplateContent>  
  <Project File="WindowsApplication.csproj" ReplaceParameters="true">  
    <ProjectItem ReplaceParameters="true"  
      TargetFileName="Properties\AssemblyInfo.cs">  
      AssemblyInfo.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Resources.resx">  
      Resources.resx  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Resources.Designer.cs">  
      Resources.Designer.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Settings.settings">  
      Settings.settings  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Settings.Designer.cs">  
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
  
 \<Projektu > Značka ovládací prvky generování projektu a \<ProjectItem > Značka ovládací prvky generování položka projektu. Pokud má parametr ReplaceParameters hodnotu true, bude přizpůsobit šablonu všech parametrů šablony v projektu soubor nebo položka. V takovém případě všechny položky projektu jsou přizpůsobené, s výjimkou Settings.settings.  
  
 Parametr TargetFileName Určuje název a relativní cestu výsledný soubor projektu nebo položky. To vám umožní vytvořit strukturu složek pro váš projekt. Pokud nezadáte tento argument, položka projektu bude mít stejný název jako šablony položek projektu.  
  
 Výsledná struktura složek aplikace Windows vypadá takto:  
  
 ![SimpleSolution](../../extensibility/internals/media/simplesolution.png "SimpleSolution")  
  
 První a pouze \<Projekt > značku čtení šablony:  
  
```  
<Project File="WindowsApplication.csproj" ReplaceParameters="true">  
```  
  
 Tím se nastaví nový projekt šablony k vytvoření souboru projektu Simple.csproj kopírování a přizpůsobením windowsapplication.csproj položky šablony.  
  
### <a name="designers-and-references"></a>Návrháři a odkazy  
 Uvidíte v Průzkumníku řešení, zda se složka vlastnosti je k dispozici a obsahuje očekávané soubory. Ale co o projekt odkazuje na a návrháři soubor závislosti, jako je například Resources.Designer.cs k Resources.resx a Form1.Designer.cs k Form1.cs?  Tyto jsou nastavené v souboru Simple.csproj kdy se generují.  
  
 Tady je \<ItemGroup > z Simple.csproj, který vytváří odkazy na projekt:  
  
```  
<ItemGroup>  
    <Reference Include="System" />  
    <Reference Include="System.Data" />  
    <Reference Include="System.Deployment" />  
    <Reference Include="System.Drawing" />  
    <Reference Include="System.Windows.Forms" />  
    <Reference Include="System.Xml" />  
</ItemGroup>  
```  
  
 Uvidíte, že jsou odkazy na šesti projektu, které se zobrazují v Průzkumníku řešení. Zde je část z jiné \<ItemGroup >. Počet řádků kódu pro přehlednost byl odstraněn. V této části, bude Settings.Designer.cs závisí na Settings.settings:  
  
```  
<ItemGroup>  
    <Compile Include="Properties\Settings.Designer.cs">  
        <DependentUpon>Settings.settings</DependentUpon>  
    </Compile>  
</ItemGroup>  
```  
  
## <a name="see-also"></a>Viz také  
 [Nová generace projektů: Pod pokličkou, část první](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)  
 [MSBuild](../../msbuild/msbuild.md)
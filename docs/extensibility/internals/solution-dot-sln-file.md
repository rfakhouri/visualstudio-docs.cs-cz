---
title: Řešení (. Soubor SLN)
ms.date: 03/15/2019
ms.topic: conceptual
helpviewer_keywords:
- sln files, VSPackages
- solutions, .sln files
- .sln files, VSPackages
ms.assetid: 7d7ef539-2e4b-4637-b853-8ec7626609df
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30b0e0b09b12dca964958d5d7b35c6b0d83906fa
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322602"
---
# <a name="solution-sln-file"></a>Soubor řešení (.sln)

Řešení je struktura pro organizování projektů v sadě Visual Studio. Řešení udržuje informace o stavu pro projekty ve dvou souborech:

- soubor .sln (založený na textu, sdílené)

- soubor .suo (binární, uživatelská řešení možnosti)

Další informace o souborech .suo, naleznete v tématu [uživatelské možnosti řešení (. Soubor suo)](../../extensibility/internals/solution-user-options-dot-suo-file.md).

Pokud je vaše VSPackage načten v důsledku, na kterou se odkazuje v souboru .sln, prostředí volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> ke čtení v souboru .sln.

Soubor .sln obsahuje textové informace, které prostředí používá k vyhledání a načtení název hodnota parametrů trvalých dat a projekt odkazuje na balíčky VSPackages. Když uživatel otevře řešení, prostředí procházení `preSolution`, `Project`, a `postSolution` informace v souboru .sln načtení řešení, projekty v řešení a žádné informace o trvalé připojené k řešení.

Každý projekt soubor obsahuje další informace, přečtěte si prostředí k naplnění hierarchie s položky tohoto projektu. Trvalost dat hierarchie se řídí tím projekt. Data se obvykle uložená v souboru .sln, sice můžou záměrně zapisovat informace o projektu soubor .sln, pokud budete chtít udělat. Další informace o trvalosti najdete v tématu [trvalost projektu](../../extensibility/internals/project-persistence.md) a [otevření a uložení položek projektu](../../extensibility/internals/opening-and-saving-project-items.md).

## <a name="file-header"></a>Hlavička souboru

Hlavička souboru .sln vypadá takto:

::: moniker range="vs-2017"

```
Microsoft Visual Studio Solution File, Format Version 12.00
# Visual Studio 15
VisualStudioVersion = 15.0.26730.15
MinimumVisualStudioVersion = 10.0.40219.1
```

### <a name="definitions"></a>Definice

`Microsoft Visual Studio Solution File, Format Version 12.00`\
Standardní hlavička, který definuje formát verze souboru.

`# Visual Studio 15`\
Hlavní verze sady Visual Studio (naposledy) uložit tento soubor řešení. Tyto informace Určuje číslo verze v ikonu řešení.

`VisualStudioVersion = 15.0.26730.15`\
Plnou verzi sady Visual Studio (naposledy) uložit soubor řešení. Pokud soubor řešení je uložen v novější verzi sady Visual Studio, který má stejnou hlavní verzi, tato hodnota je aktualizována tak, aby se změny v souborech řešení zmenšit.

`MinimumVisualStudioVersion = 10.0.40219.1`\
Minimální verze (nejstarší) sady Visual Studio, můžete otevřít tento soubor řešení.

::: moniker-end

::: moniker range=">=vs-2019"

```
Microsoft Visual Studio Solution File, Format Version 12.00
# Visual Studio Version 16
VisualStudioVersion = 16.0.28701.123
MinimumVisualStudioVersion = 10.0.40219.1
```

### <a name="definitions"></a>Definice

`Microsoft Visual Studio Solution File, Format Version 12.00`\
Standardní hlavička, který definuje formát verze souboru.

`# Visual Studio Version 16`\
Hlavní verze sady Visual Studio (naposledy) uložit tento soubor řešení. Tyto informace Určuje číslo verze v ikonu řešení.

`VisualStudioVersion = 16.0.28701.123`\
Plnou verzi sady Visual Studio (naposledy) uložit soubor řešení. Pokud soubor řešení je uložen v novější verzi sady Visual Studio, který má stejnou hlavní verzi, není tato hodnota aktualizuje tak, aby snížit četnosti změn v souboru.

`MinimumVisualStudioVersion = 10.0.40219.1`\
Minimální verze (nejstarší) sady Visual Studio, můžete otevřít tento soubor řešení.

::: moniker-end

## <a name="file-body"></a>Text souboru

Soubor .sln sestává z několika oddílů, které jsou označené jako `GlobalSection`, tímto způsobem:

```
Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1", "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"
EndProject
Global
  GlobalSection(SolutionNotes) = postSolution
  EndGlobalSection
  GlobalSection(SolutionConfiguration) = preSolution
       ConfigName.0 = Debug
       ConfigName.1 = Release
  EndGlobalSection
  GlobalSection(ProjectDependencies) = postSolution
  EndGlobalSection
  GlobalSection(ProjectConfiguration) = postSolution
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.ActiveCfg = Debug|x86
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.Build.0 = Debug|x86
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.ActiveCfg = Release|x86
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.Build.0 = Release|x86
  EndGlobalSection
  GlobalSection(ExtensibilityGlobals) = postSolution
  EndGlobalSection
  GlobalSection(ExtensibilityAddIns) = postSolution
  EndGlobalSection
EndGlobal
```

Načtení řešení, prostředí provádí následující pořadí úloh:

1. Prostředí globální části souboru .sln, načte a zpracuje všechny oddíly označené `preSolution`. V tomto příkladu souboru je jeden takový výraz:

   ```
   GlobalSection(SolutionConfiguration) = preSolution
        ConfigName.0 = Debug
        ConfigName.1 = Release
   ```

   Když prostředí přečte `GlobalSection('name')` značku, odpovídá názvu VSPackage pomocí registru. Název klíče, který by měla existovat v klíči registru [HKLM\\< kořenový adresář aplikace ID registru\>\SolutionPersistence\AggregateGUIDs]. Klíče výchozí hodnota je identifikátor GUID balíčku (REG_SZ) sady VSPackage, který napsal položky.

2. Prostředí načte sady VSPackage, volání `QueryInterface` v balíčku VSPackage pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> rozhraní a volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> metoda s daty v části sady VSPackage mohli uložit data. Prostředí tento proces se opakuje pro každý `preSolution` oddílu.

3. Prostředí iteraci projektu dočasných bloků. V takovém případě je jeden projekt.

   ```
   Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1",
   "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"
   EndProject
   ```

   Tento příkaz, který obsahuje jedinečné GUID projektu a identifikátor GUID typu projektu. Tyto informace slouží prostředí k vyhledání souboru projektu nebo soubory, které patří k řešení, a pro každý projekt se nevyžaduje sady VSPackage. Projekt je předat identifikátor GUID <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> načíst konkrétní VSPackage související s projektem, pak projekt je načten prostřednictvím sady VSPackage. V tomto případě je sady VSPackage, která jsou načtená pro tento projekt jazyka Visual Basic.

   Každý projekt můžete zachovat a projektu Jedinečný ID instance, tak, aby k němu podle potřeby jiné projekty v řešení. V ideálním případě pokud řešení a projekty jsou pod správou zdrojového kódu, cesta k projektu by měla být relativní k cestě k řešení. Při prvním načtení řešení, soubory projektu nemohou být na počítači uživatele. Tím, že soubor projektu, které jsou uloženy na serveru relativní k souboru řešení, je poměrně jednoduchá pro soubor projektu a najít a zkopírovat do počítače uživatele. Potom zkopíruje a načte zbývající soubory potřebné pro projekt.

4. Podle informací obsažených v části projektu souboru .sln, prostředí načte každého souboru projektu. Samotného projektu je pak zodpovědná za naplnění hierarchie projektu a načítání všech vnořených projektů.

5. Po zpracování všech oddílů v souboru .sln řešení se zobrazí v Průzkumníku řešení a je připravený pro úpravu uživatelem.

Pokud žádné VSPackage, která implementuje projektu v řešení se nepodaří načíst, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.OnProjectLoadFailure%2A> volání metody a každý projekt v řešení je zadána možnost Ignorovat změny, které jste zadali během načítání. Pokud dojde k chybám analýzy, co nejvíce informací se zachovají se soubory řešení a prostředí se zobrazí dialogové okno s upozorněním, že řešení je poškozený.

Když toto řešení je uložen nebo closed, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.QuerySaveSolutionProps%2A> metoda je volána a předané do hierarchie, které chcete zobrazit, pokud byly provedeny změny do řešení, které je nutné zadat do souboru .sln. Hodnota null, předaná `QuerySaveSolutionProps` v <xref:Microsoft.VisualStudio.Shell.Interop.VSQUERYSAVESLNPROPS>, označuje, že se se informace ukládají pro řešení. Pokud hodnota není null, trvalé informace se týkají určitého projektu, určené ukazatel <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> rozhraní.

Pokud nejsou k dispozici informace uložit, <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> rozhraní je volána pomocí ukazatele na <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.SaveSolutionProps%2A> metody. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> Metoda je volána poté prostředí k načtení dvojice název hodnota z `IPropertyBag` rozhraní a zápisu informací do souboru .sln.

`SaveSolutionProps` a `WriteSolutionProps` objekty jsou volány rekurzivně prostředí k načtení informací z Uložit `IPropertyBag` rozhraní, dokud se všechny změny byly zadány do souboru .sln. Tímto způsobem můžete zajistit, že se zachovat informace pomocí řešení a k dispozici příštím otevření řešení.

Všechny načtené VSPackage je vypočten a zjistěte, jestli má něco uložit do souboru .sln. Je pouze v době zatížení, který se generuje dotaz na klíče registru. Prostředí ví o všech načtených balíčků, protože jsou v době, kdy je řešení uloženo v paměti.

Pouze soubor .sln obsahuje položky `preSolution` a `postSolution` oddíly. Nejsou žádné podobné oddílů v souboru .suo, protože toto řešení vyžaduje tyto informace načíst správně. Soubor .suo obsahuje možnosti specifické pro uživatele, jako jsou privátní poznámky, které nejsou určeny k sdílená nebo je umístěn pod správou zdrojového kódu.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>
- [Soubor uživatelských možností řešení (.Suo)](../../extensibility/internals/solution-user-options-dot-suo-file.md)
- [Řešení](../../extensibility/internals/solutions-overview.md)
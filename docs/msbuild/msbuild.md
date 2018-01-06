---
title: MSBuild | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, about MSBuild
- MSBuild, overview
ms.assetid: e39f13f7-1e1d-4435-95ca-0c222bca071c
caps.latest.revision: "59"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4e809363656b94dc4e922d558a57a0848dba46e0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild"></a>MSBuild
[!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] Je platforma pro vytváření aplikací. Tento modul, který je také označován jako MSBuild, poskytuje schéma XML pro soubor projektu, který určuje, jak platformy sestavení zpracuje a vytvoří softwaru. Visual Studio použije nástroje MSBuild, ale není závisí na sadě Visual Studio. Vyvoláním msbuild.exe v souboru projektu nebo řešení můžete orchestraci a sestavení produkty v prostředích, kde není nainstalovaná sada Visual Studio.  
  
 Visual Studio použije nástroje MSBuild k načtení a vytvoření spravované projekty. Soubory projektu v sadě Visual Studio (.csproj, .vbproj, vcxproj a dalších) obsahovat kód MSBuild XML, který se spustí při sestavování projektu s použitím prostředí IDE. Importovat všechny potřebné nastavení projektů sady Visual Studio a sestavení procesy udělat typické vývoji, ale mohou rozšířit nebo je z upravit v sadě Visual Studio nebo pomocí editoru XML.  
  
 Informace o nástroji MSBuild pro jazyk C++ najdete v tématu [MSBuild (Visual C++)](/cpp/build/msbuild-visual-cpp).  
  
 Následující příklady znázorňují při sestavení může spustit pomocí příkazového řádku s MSBuild místo Visual Studio IDE.  
  
-   Visual Studio není nainstalována.  
  
-   Chcete použít 64bitovou verzi nástroje MSBuild. Tato verze nástroje MSBuild je obvykle není zapotřebí, ale umožňuje MSBuild pro přístup k více paměti.  
  
-   Chcete spustit sestavení ve více procesů. Můžete však použít rozhraní IDE k dosažení stejného výsledku v projektech v jazyce C++ a C#.  
  
-   Chcete-li upravit systém sestavení. Například můžete chtít povolit následující akce:  
  
    -   Předběžné zpracování souborů než dosáhnou kompilátoru.  
  
    -   Zkopírujte sestavení výstupy na jiné místo.  
  
    -   Vytvořte komprimované soubory z výstupů sestavení.  
  
    -   Proveďte následného zpracování krok. Například můžete chtít razítka sestavení s jinou verzi.  
  
 Můžete napsat kód v prostředí Visual Studio IDE, ale spustit sestavení pomocí nástroje MSBuild. Jako další možnost vytvoření kódu v prostředí IDE ve vývojovém počítači, ale pomocí příkazového řádku s MSBuild sestavení kódu, který je integrován z více vývojářů.  
  
> [!NOTE]
>  Team Foundation Build můžete použít pro automaticky kompilovat, testování a nasazení aplikace. Sestavení systému můžete automaticky spustit sestavení, když vývojáři změnami kódu (například jako součást strategie průběžnou integraci) nebo podle plánu (například noční sestavení sestavení ověřovací Test). Team Foundation Build zkompiluje kódu pomocí nástroje MSBuild. Další informace najdete v tématu [sestavení aplikace](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692).  
  
 Toto téma obsahuje přehled nástroje MSBuild. Úvodní kurz, najdete v části [návod: použití nástroje MSBuild](../msbuild/walkthrough-using-msbuild.md).  
  
 **V tomto tématu**  
  
-   [Pomocí nástroje MSBuild v příkazovém řádku](#BKMK_CommandPrompt)  
  
-   [Soubor projektu](#BKMK_ProjectFile)  
  
    -   [Vlastnosti](#BKMK_Properties)  
  
    -   [Položky](#BKMK_Items)  
  
    -   [Úlohy](#BKMK_Tasks)  
  
    -   [Cíle](#BKMK_Targets)  
  
-   [Sestavení protokoly](#BKMK_BuildLogs)  
  
-   [Pomocí nástroje MSBuild v sadě Visual Studio](#BKMK_VisualStudio)  
  
-   [Cílení na více verzí](#BKMK_Multitargeting)  
  
##  <a name="BKMK_CommandPrompt"></a>Pomocí nástroje MSBuild v příkazovém řádku  
 Ke spuštění [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] na příkazovém řádku, předat soubor projektu do MSBuild.exe, společně s možnosti příkazového řádku. Možnosti příkazového řádku umožňují nastavit vlastnosti, provést určité cíle a nastavte další možnosti, které řídí procesu sestavení. Třeba, použijte následující syntaxi příkazového řádku k vytvoření souboru `MyProj.proj` s `Configuration` vlastnost nastavena na hodnotu `Debug`.  
  
```  
MSBuild.exe MyProj.proj /property:Configuration=Debug  
```  
  
 Další informace o [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] možnosti příkazového řádku najdete v tématu [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md).  
  
> [!IMPORTANT]
>  Před stažením projektu určete důvěryhodnosti kódu.  
  
##  <a name="BKMK_ProjectFile"></a>Soubor projektu  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]používá formát souborů projektu na základě XML, který je snadný a rozšiřitelný. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Formát souboru projektu umožňuje vývojářům popisují položky, které se má být sestaven, a také způsob jejich má být sestaven pro jiné operační systémy a konfigurace. Kromě toho formát souboru projektu umožňuje vývojářům vytvořit opakovaně použitelný sestavení pravidla, která může být rozdělen do samostatné soubory tak, že sestavení můžete provedeny konzistentně napříč různé projekty v rámci produktu.  
  
 Následující části popisují některé základní prvky [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] formát souboru projektu. Kurz o tom, jak vytvořit základní projekt soubor, najdete v části [návod: vytvoření souboru projektu MSBuild od začátku](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md).  
  
###  <a name="BKMK_Properties"></a>Vlastnosti  
 Vlastnosti představují páry klíč/hodnota, které můžete použít ke konfiguraci sestavení. Vlastnosti jsou deklarovány vytvořením element, který má název vlastnosti jako podřízenou [PropertyGroup](../msbuild/propertygroup-element-msbuild.md) elementu. Například následující kód vytvoří vlastnost s názvem `BuildDir` , má hodnotu `Build`.  
  
```xml  
<PropertyGroup>  
    <BuildDir>Build</BuildDir>  
</PropertyGroup>  
```  
  
 Můžete definovat vlastnost podmíněně umístěním `Condition` atribut v elementu. Obsah podmíněného elementů se ignoruje, pokud je podmínka vyhodnocena jako `true`. V následujícím příkladu `Configuration` element je definována, pokud ještě nebyl definován.  
  
```xml  
<Configuration  Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
```  
  
 Vlastnosti lze odkazovat v souboru projektu pomocí syntaxe $(*PropertyName*). Například vlastnosti v předchozích příkladech můžete odkazovat pomocí `$(BuildDir)` a `$(Configuration)`.  
  
 Další informace o vlastnostech najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).  
  
###  <a name="BKMK_Items"></a>Položky  
 Položky jsou vstupy do systému sestavení a obvykle představují soubory. Položky jsou seskupeny do typů položek, na základě názvů uživatelem definovanou položku. Tyto typy položek můžete použít jako parametry pro úlohy, které používají jednotlivé položky k provedení kroků procesu sestavení.  
  
 Položky jsou deklarované v souboru projektu vytvořením element, který má název typu položky jako podřízenou [ItemGroup](../msbuild/itemgroup-element-msbuild.md) element. Například následující kód vytvoří typ položky s názvem `Compile`, což zahrnuje dva soubory.  
  
```xml  
<ItemGroup>  
    <Compile Include = "file1.cs"/>  
    <Compile Include = "file2.cs"/>  
</ItemGroup>  
```  
  
 Typy položek lze odkazovat v souboru projektu pomocí syntaxe @(*ItemType*). Typ položky v příkladu by například odkazovat pomocí `@(Compile)`.  
  
 V nástroji MSBuild jsou názvy elementu a atributu malá a velká písmena. Názvy vlastností, položky a metadata jsou však není. Následující příklad vytvoří typ položky `Compile`, `comPile`, nebo jiné případu variace a dává typ položky hodnotu "one.cs;two.cs".  
  
```xml  
<ItemGroup>  
  <Compile Include="one.cs" />  
  <comPile Include="two.cs" />  
</ItemGroup>  
```  
  
 Položky lze deklarovat pomocí zástupných znaků a může obsahovat další metadata pro pokročilejší scénáře sestavení. Další informace o položkách najdete v tématu [položky](../msbuild/msbuild-items.md).  
  
###  <a name="BKMK_Tasks"></a>Úlohy  
 Úlohy jsou jednotky spustitelného kódu, který [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty používají k provádění operací sestavení. Úloha může být například kompilaci vstupní soubory nebo spuštění externího nástroje. Úlohy lze znovu použít, a je může sdílet různé vývojáři v různých projektů.  
  
 Logika spuštění úlohy je zapsané ve spravovaném kódu a mapované na [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pomocí [usingtask –](../msbuild/usingtask-element-msbuild.md) elementu. Můžete napsat vlastní úlohy vytvářením spravovaný typ, který implementuje <xref:Microsoft.Build.Framework.ITask> rozhraní. Další informace o tom, jak psát úlohy najdete v tématu [zápis úloh](../msbuild/task-writing.md).  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]obsahuje běžné úkoly, které lze upravit podle svých potřeb.  Příklady [kopie](../msbuild/copy-task.md), který zkopíruje soubory, [makedir –](../msbuild/makedir-task.md), vytváří adresáře a [Csc](../msbuild/csc-task.md), který zkompiluje soubory zdrojového kódu Visual C#. Seznam dostupných úloh společně s informace o použití najdete v tématu [– Reference úlohy](../msbuild/msbuild-task-reference.md).  
  
 Úloha se spustí v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubor projektu vytvořením element, který má název úlohy jako podřízenou [cíl](../msbuild/target-element-msbuild.md) elementu. Úlohy jsou obvykle přijmout parametry, které jsou předány jako atributy elementu. Obě [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vlastností a položek lze použít jako parametry. Například následující kód volání [makedir –](../msbuild/makedir-task.md) úkolů a předává je hodnota `BuildDir` vlastnost, která byla definována v předchozího příkladu.  
  
```xml  
<Target Name="MakeBuildDirectory">  
    <MakeDir  Directories="$(BuildDir)" />  
</Target>  
```  
  
 Další informace o úlohách najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).  
  
###  <a name="BKMK_Targets"></a>Cíle  
 Cíle seskupíte úlohy v určitém pořadí a vystavit části souboru projektu jako vstupní body do procesu sestavení. Cíle jsou často seskupeny do logických částí zvýšit čitelnost a povolit pro rozšíření. Rozdělení kroky sestavení do cíle umožňuje volání jednu část procesu sestavení z jiné cíle bez kopírování této části kódu do každé cílové. Například pokud několik vstupní body do procesu sestavení vyžadují odkazy, které má být sestaven, můžete vytvořit cíl, který odkazuje na sestavení a pak spusťte cílených z každé vstupního bodu, kde je to požadováno.  
  
 Cíle jsou deklarované v souboru projektu pomocí [cíl](../msbuild/target-element-msbuild.md) elementu. Například následující kód vytvoří cíl s názvem `Compile`, který potom volá [Csc](../msbuild/csc-task.md) úlohu, která má seznamu položku, která byla definována v předchozího příkladu.  
  
```xml  
<Target Name="Compile">  
    <Csc Sources="@(Compile)" />  
</Target>  
```  
  
 V pokročilejší scénáře cíle lze popsat vztahy mezi sebou a provádět analýzy závislost tak, aby celý části procesu sestavení mohou být přeskočeny, pokud tento cíl je aktuální. Další informace o cílech najdete v tématu [cíle](../msbuild/msbuild-targets.md).  
  
##  <a name="BKMK_BuildLogs"></a>Sestavení protokoly  
 Sestavení chyby, upozornění a zprávy se můžou přihlásit na konzole nebo jiné výstupní zařízení. Další informace najdete v tématu [získání sestavení protokoly](../msbuild/obtaining-build-logs-with-msbuild.md) a [protokolování v nástroji MSBuild](../msbuild/logging-in-msbuild.md).  
  
##  <a name="BKMK_VisualStudio"></a>Pomocí nástroje MSBuild v sadě Visual Studio  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]používá [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] formát souboru projektu k uložení sestavení informací o spravovaných projekty. Nastavení, které se přidají nebo změnit pomocí projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozhraní se projeví v. * proj soubor, který se vygeneruje pro každý projekt. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]používá hostované instanci [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] k vytvoření spravovaného projektů. To znamená, že spravovaný projekt může být součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebo na příkazovém řádku (i když [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] není nainstalována), a výsledky musí být stejný.  
  
 Kurz týkající se použití nástroje MSBuild v sadě Visual Studio, najdete v části [návod: použití nástroje MSBuild](../msbuild/walkthrough-using-msbuild.md).  
  
##  <a name="BKMK_Multitargeting"></a>Cílení na více verzí  
 Pomocí sady Visual Studio můžete zkompilovat aplikace pro spuštění na libovolném několik verzí rozhraní .NET Framework. Například můžete zkompilovat aplikaci spustit v rozhraní .NET Framework 2.0 na 32bitové platformě a zkompilujete stejnou aplikaci spustit v rozhraní .NET Framework 4.5 na 64bitové platformě. Možnost zkompilovat více než jeden Framework jmenuje cílení na více verzí.  
  
 Toto jsou některé z výhod cílení na více verzí:  
  
-   Můžete vyvíjet aplikace, které mají starší verze rozhraní .NET Framework, například verze 2.0, 3.0 a 3.5.  
  
-   Můžete určit cílovou rozhraní než rozhraní .NET Framework, například Silverlight.  
  
-   Můžete se zaměřit *profil framework*, což je předdefinovaná část cílové rozhraní.  
  
-   Pokud vydání aktualizace service pack pro aktuální verze rozhraní .NET Framework, může ho cíle.  
  
-   Cílení na více verzí zaručuje, že aplikace používá jenom funkce, které jsou k dispozici v cílové architektury a platformu.  
  
 Další informace najdete v tématu [cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Návod: Vytvoření souboru projektu MSBuild od začátku](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)|Ukazuje, jak vytvořit základní projekt soubor postupně, pomocí pouze textový editor.|  
|[Návod: Použití nástroje MSBuild](../msbuild/walkthrough-using-msbuild.md)|Nabízí jako stavební bloky pro MSBuild a ukazuje, jak k zápisu, manipulaci a ladění projektů MSBuild bez ukončení Visual Studio IDE.|  
|[Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)|Uvede čtyři stavební bloky nástroje MSBuild: vlastnosti, položky, cílů a úloh.|  
|[Položky](../msbuild/msbuild-items.md)|Popisuje obecné koncepty za [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru formátu a jak jsou navzájem propojené částí do jednoho.|  
|[Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)|Představuje vlastnosti a vlastnosti kolekce. Vlastnosti jsou páry klíč/hodnota, které můžete použít ke konfiguraci sestavení.|  
|[Cíle](../msbuild/msbuild-targets.md)|Vysvětluje, jak povolit části procesu sestavení, která se má volat na příkazovém řádku a skupiny úlohy společně v určitém pořadí.|  
|[Úlohy](../msbuild/msbuild-tasks.md)|Ukazuje, jak vytvořit jednotku spustitelného kódu, který mohou využívat [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] k provádění operací atomic sestavení.|  
|[Podmínky](../msbuild/msbuild-conditions.md)|Popisuje postup použití `Condition` atribut elementu MSBuild.|  
|[Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)|Uvede dávkování, provádění transformací, cílení na více verzí a další pokročilé techniky.|  
|[Protokolování v nástroji MSBuild](../msbuild/logging-in-msbuild.md)|Popisuje, jak do protokolu událostí sestavení, zpráv a chyby.|  
|[Další zdroje informací](../msbuild/additional-msbuild-resources.md)|Obsahuje seznam podpory a komunitních zdrojů pro další informace o nástroji MSBuild.|  
  
## <a name="reference"></a>Odkaz  
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)  
 Odkazy na témata, které obsahují referenční informace.  
  
 [Glosář](msbuild-glossary.md) definuje běžné podmínky nástroje MSBuild.

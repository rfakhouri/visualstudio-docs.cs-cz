---
title: "Úlohy nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#MSBuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild task [MSBuild]
- MSBuild, MSBuild task
ms.assetid: 76577f6c-7669-44ad-a840-363e37a04d34
caps.latest.revision: "32"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 264b5b379b7c3f2fa364d01260e1da825b5d64d8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-task"></a>MSBuild – úloha
Sestavení [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty z jiné [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `MSBuild` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`BuildInParallel`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, projekty, zadaný v `Projects` parametru jsou vytvořené paralelně, pokud je to možné. Výchozí hodnota je `false`.|  
|`Projects`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje soubory projektu, k vytvoření.|  
|`Properties`|Volitelné `String` parametr.<br /><br /> Seznam dvojic název hodnota vlastnosti použít jako globální vlastnosti projektu podřízené oddělených středníky. Při zadání tohoto parametru je funkčně srovnatelný nastavení vlastností, které mají **/property** přepínače při sestavování s [MSBuild.exe](../msbuild/msbuild-command-line-reference.md). Příklad:<br /><br /> `Properties="Configuration=Debug;Optimize=$(Optimize)"`<br /><br /> Pokud předáte vlastnosti projektu prostřednictvím `Properties` parametr [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vytvoří novou instanci třídy projektu i v případě, že soubor projektu byl již načten. Po vytvoření nové instance projektu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] považuje za jiný projekt, který má jiné vlastnosti globálních a které se dají vytvářet paralelně s další instance projektu. Konfigurace verze může například vytvořit ve stejnou dobu jako konfiguraci ladění.|  
|`RebaseOutputs`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, relativní cesty cíle výstupní položky z integrované projekty mají jejich cestách, upraví se relativně k volání projektu. Výchozí hodnota je `false`.|  
|`RemoveProperties`|Volitelné `String` parametr.<br /><br /> Určuje sadu globální vlastnosti, které chcete odebrat.|  
|`RunEachTargetSeparately`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úloh vyvolá každý cíl v seznamu předaný [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] jeden po druhém, místo ve stejnou dobu. Nastavení tohoto parametru na `true` zaručuje, že následné cíle jsou vyvolány i v případě, že dříve vyvolaná cíle se nezdařilo. Chyby sestavení, jinak by zastavit vyvolání všechny následné cíle. Výchozí hodnota je `false`.|  
|`SkipNonexistentProjects`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, soubory projektu, které nejsou k dispozici na disku se přeskočí. Takové projekty, jinak dojde k chybě.|  
|`StopOnFirstFailure`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, pokud jeden z projektů nepodaří vytvořit, budou vytvořeny žádné další projekty. Aktuálně nejsou podporované při sestavování paralelně (s více procesory).|  
|`TargetAndPropertyListSeparators`|Volitelné `String[]` parametr.<br /><br /> Určuje seznam cílů a vlastnosti jako `Project` metadata položky). Oddělovače bude zrušení uvozený před zpracováním. například % 3B (uvozovacími znaky ';') nakládáno, jako by šlo zrušení uvozený ';'.|  
|`TargetOutputs`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` jen pro čtení výstupní parametr.<br /><br /> Vrátí výstupy z předdefinovaných cílů z všechny soubory projektu. Pouze výstupy z cílů, které byly zadány jsou vráceny, ne všechny výstupy, které mohou existovat na cíle, které jsou závislé na těchto cílů.<br /><br /> `TargetOutputs` Parametr taky obsahuje následující metadata:<br /><br /> -   `MSBuildSourceProjectFile`: [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Soubor projektu, který obsahuje cíl, který nastavit výstupy.<br />-   `MSBuildSourceTargetName`: Cíl, který nastavit výstupy. **Poznámka:** Pokud chcete identifikovat výstupy z každého souboru projektu nebo cíle samostatně, spusťte `MSBuild` úloh samostatně pro každý soubor projektu nebo cíl. Pokud spustíte `MSBuild` úkolů pouze jednou, pokud chcete vytvořit všechny soubory projektu, výstupy všechny cíle se shromáždí do jednoho pole.|  
|`Targets`|Volitelné `String` parametr.<br /><br /> Určuje cílový nebo cíle k sestavení v souborech projektu. K oddělení seznam názvů cíl použijte středník. Pokud nejsou zadány žádné cíle v `MSBuild` úloh, výchozí cíle uvedená v souborech projektu jsou vytvořeny. **Poznámka:** cíle se musí vyskytovat v všechny soubory projektu. Pokud ne, dojde k chybě sestavení.|  
|`ToolsVersion`|Volitelné `String` parametr.<br /><br /> Určuje, `ToolsVersion` pro použití při sestavování projektů předaný této úlohy.<br /><br /> Umožňuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úloh pro sestavení projektu, jehož cílem jinou verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] než verze zadaná v projektu. Platné hodnoty jsou `2.0`, `3.0` a `3.5`. Výchozí hodnota je `3.5`.|  
|`UnloadProjectsOnCompletion`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, projekt bude zrušeno po dokončení operace.|  
|`UseResultsCache`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, výsledky uložené v mezipaměti bude vrácen, pokud je k dispozici. Pokud je theMSBuild úloha spuštěna, bude jeho výsledek v oboru (ProjectFileName, GlobalProperties) do mezipaměti [TargetNames]<br /><br /> jako seznam položek sestavení|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
 Na rozdíl od použití [Exec – úloha](../msbuild/exec-task.md) zahájíte MSBuild.exe tato úloha používá stejnou [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] procesu k vytvoření projektů, podřízený objekt. Seznam cílů už sestavené, které mohou být přeskočeny jsou sdílena mezi nadřazenými a podřízenými sestavení. Tato úloha je také rychlejší, protože nové [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proces je vytvořen.  
  
 Tato úloha může zpracovat pouze soubory projektu, ale také soubory řešení.  
  
 Jakákoli konfigurace, který je požadován [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] povolit projekty k sestavení ve stejnou dobu, i v případě konfigurace zahrnuje vzdálené infrastruktury (například porty, protokoly, časové limity, opakování a tak dále), musí být provedeny konfigurovat pomocí konfigurační soubor. Pokud je to možné, položky konfigurace by mohli být zadány jako parametry úlohy na `MSBuild` úloh.  
  
 Počínaje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5, řešení projekty nyní prostor TargetOutputs ze všech podřízených projektů sestavuje.  
  
## <a name="passing-properties-to-projects"></a>Předávání vlastností do projektů  
 Ve verzích [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] před [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5, předávání různých nastaví vlastností do různých projektů, které jsou uvedené v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] položka byla náročná. Pokud jste použili atribut vlastnosti [úlohy nástroje MSBuild](../msbuild/msbuild-task.md), a jeho nastavení se použije na všechny projekty sestavuje, pokud jste zpracovat v dávce [úlohy nástroje MSBuild](../msbuild/msbuild-task.md) a podmíněně poskytuje různé vlastnosti pro každý projekt, v seznamu položek.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]3.5, ale nabízí dvě nové vyhrazené položky metadat, vlastnosti a možnost AdditionalProperties, která umožňují flexibilní způsob, jak předat jiné vlastnosti pro různé projekty vrácení vyvíjené [úlohy nástroje MSBuild](../msbuild/msbuild-task.md).  
  
> [!NOTE]
>  Tyto nové položky metadat se vztahují pouze na položek předaných v atributu projekty [úlohy nástroje MSBuild](../msbuild/msbuild-task.md).  
  
## <a name="multi-processor-build-benefits"></a>Výhody víceprocesorového sestavení  
 Mezi hlavní výhody použití této novými metadaty nastane, když vytváříte projekty paralelně na systému s více procesory. Metadata umožňuje sloučit všechny projekty do jednoho [úlohy nástroje MSBuild](../msbuild/msbuild-task.md) volání bez nutnosti provádět žádné dávkování nebo podmíněného [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úlohy. A při volání jedné [úlohy nástroje MSBuild](../msbuild/msbuild-task.md), všechny projekty uvedené v atributu projekty budou vytvořeny paralelně. (Jenom, ale, pokud `BuildInParallel=true` atribut je součástí [úlohy nástroje MSBuild](../msbuild/msbuild-task.md).) Další informace najdete v tématu [sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).  
  
## <a name="properties-metadata"></a>Vlastnosti metadat  
 Obvyklým scénářem je při vytváření více souborů řešení pomocí [úlohy nástroje MSBuild](../msbuild/msbuild-task.md), pouze pomocí konfigurace jiné sestavení. Můžete chtít vytvořit řešení a1 pomocí ladění konfiguraci a řešení a2 pomocí konfigurace verze. V [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0, tento projektový soubor bude vypadat třeba takto:  
  
> [!NOTE]
>  V následujícím příkladu "..." představuje soubory další řešení.  
  
### <a name="aproj"></a>a.proj  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="Build">  
        <MSBuild Projects="a1.sln..." Properties="Configuration=Debug"/>  
        <MSBuild Projects="a2.sln" Properties="Configuration=Release"/>  
    </Target>  
</Project>  
```  
  
 Pomocí vlastnosti metadat však můžete zjednodušit tím používat jeden [úlohy nástroje MSBuild](../msbuild/msbuild-task.md), jak ukazují následující:  
  
### <a name="aproj"></a>a.proj  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ProjectToBuild Include="a1.sln...">  
            <Properties>Configuration=Debug</Properties>  
        </ProjectToBuild>  
        <ProjectToBuild Include="a2.sln">  
            <Properties>Configuration=Release</Properties>  
        </ProjectToBuild>  
    </ItemGroup>  
    <Target Name="Build">  
        <MSBuild Projects="@(ProjectToBuild)"/>  
    </Target>  
</Project>  
```  
  
 \-nebo –  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ProjectToBuild Include="a1.sln..."/>  
        <ProjectToBuild Include="a2.sln">  
            <Properties>Configuration=Release</Properties>  
        </ProjectToBuild>  
    </ItemGroup>  
    <Target Name="Build">  
        <MSBuild Projects="@(ProjectToBuild)"   
          Properties="Configuration=Debug"/>  
    </Target>  
</Project>  
```  
  
## <a name="additionalproperties-metadata"></a>Metadata AdditionalProperties  
 Vezměte v úvahu následující scénář, kde vytváříte dva soubory řešení pomocí [úlohy nástroje MSBuild](../msbuild/msbuild-task.md), jak pomocí konfigurace verze, ale jeden pomocí x86 architektura a dalších pomocí architektury ia64. V [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0, museli byste vytvořit více instancí [úlohy nástroje MSBuild](../msbuild/msbuild-task.md): jeden pro sestavení projektu verzi konfigurace pomocí x86 architekturu, jiné verzi konfigurace pomocí ia64 Architektura. Soubor projektu by vypadat následovně:  
  
### <a name="aproj"></a>a.proj  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="Build">  
        <MSBuild Projects="a1.sln..." Properties="Configuration=Release;   
          Architecture=x86"/>  
        <MSBuild Projects="a2.sln" Properties="Configuration=Release;   
          Architecture=ia64"/>  
    </Target>  
</Project>  
```  
  
 Na základě metadat možnost AdditionalProperties, můžete zjednodušit k použití jedné [úlohy nástroje MSBuild](../msbuild/msbuild-task.md) pomocí následujícího:  
  
### <a name="aproj"></a>a.proj  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ProjectToBuild Include="a1.sln...">  
            <AdditionalProperties>Architecture=x86  
              </AdditionalProperties>  
        </ProjectToBuild>  
        <ProjectToBuild Include="a2.sln">  
            <AdditionalProperties>Architecture=ia64  
              </AdditionalProperties>  
        </ProjectToBuild>  
    </ItemGroup>  
    <Target Name="Build">  
        <MSBuild Projects="@(ProjectToBuild)"   
          Properties="Configuration=Release"/>  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `MSBuild` úloh pro sestavení projektů určeného `ProjectReferences` kolekce položek. Výsledný cíl výstupy jsou uložené v `AssembliesBuiltByChildProjects` kolekce položek.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <ProjectReferences Include="*.*proj" />  
    </ItemGroup>  
  
    <Target Name="BuildOtherProjects">  
        <MSBuild  
            Projects="@(ProjectReferences)"  
            Targets="Build">  
            <Output  
                TaskParameter="TargetOutputs"  
                ItemName="AssembliesBuiltByChildProjects" />  
        </MSBuild>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
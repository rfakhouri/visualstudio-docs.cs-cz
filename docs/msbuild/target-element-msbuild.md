---
title: "Cíl – Element (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#Target
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Target element [MSBuild]
- <Target> element [MSBuild]
ms.assetid: 350f6fc2-86b3-45f2-a31e-ece0e6bd4dca
caps.latest.revision: "34"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3e8a444add9d28a79458dabab75b4cf62bf951dc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="target-element-msbuild"></a>Target – element (MSBuild)
Obsahuje sadu úloh pro [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] postupně provést.  

 \<Projekt >  
 \<Cíl >  

## <a name="syntax"></a>Syntaxe  

```  
<Target Name="Target Name"  
        Inputs="Inputs"  
        Outputs="Outputs"  
        Returns="Returns"  
        KeepDuplicateOutputs="true/false"  
        BeforeTargets="Targets"  
        AfterTargets="Targets"  
        DependsOnTargets="DependentTarget"  
        Condition="'String A' == 'String B'">  
        Label="Label">  
    <Task>... </Task>  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <OnError... />  
</Target>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadovaný atribut.<br /><br /> Název cíle|  
|`Condition`|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Pokud je podmínka vyhodnocena jako `false`, cíl nebude provést cíl nebo veškerých cílů, které jsou nastaveny v těle `DependsOnTargets` atribut. Další informace o podmínkách najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  
|`Inputs`|Nepovinný atribut.<br /><br /> Soubory, které tvoří vstupy do tento cíl. Více souborů jsou odděleny středníky. Časová razítka souborů budou porovnány s časová razítka souborů v `Outputs` Chcete-li určit, zda `Target` je aktuální. Další informace najdete v tématu [přírůstková sestavení](../msbuild/incremental-builds.md), [postupy: sestavení přírůstkově](../msbuild/how-to-build-incrementally.md), a [transformuje](../msbuild/msbuild-transforms.md).|  
|`Outputs`|Nepovinný atribut.<br /><br /> Soubory, které formuláře výstupy do tento cíl. Více souborů jsou odděleny středníky. Časová razítka souborů budou porovnány s časová razítka souborů v `Inputs` Chcete-li určit, zda `Target` je aktuální. Další informace najdete v tématu [přírůstková sestavení](../msbuild/incremental-builds.md), [postupy: sestavení přírůstkově](../msbuild/how-to-build-incrementally.md), a [transformuje](../msbuild/msbuild-transforms.md).|  
|`Returns`|Nepovinný atribut.<br /><br /> Sada položek, které bude k dispozici pro úlohy, které vyvolají tento cíl, například úlohy nástroje MSBuild. Více cílů oddělených středníky. Pokud žádné cíle v souboru `Returns` atributy, výstupy atributy se používají místo pro tento účel.|  
|`KeepDuplicateOutputs`|Volitelný logický atribut.<br /><br /> Pokud `true`, se zaznamenávají několik odkazů na stejné položky v vrátí cílové složky.  Ve výchozím nastavení, tento atribut je `false`.|  
|`BeforeTargets`|Nepovinný atribut.<br /><br /> Seznam cílových názvů oddělených středníkem.  -Li zadána, označuje, že tento cíl měly být spuštěny před zadaný cíl nebo cíle. To umožňuje autorovi projektu rozšířit existující sady cíle beze změny je přímo. Další informace najdete v tématu [cíl sestavení pořadí](../msbuild/target-build-order.md).|  
|`AfterTargets`|Nepovinný atribut.<br /><br /> Seznam cílových názvů oddělených středníkem. -Li zadána, označuje, že tento cíl měly být spuštěny po zadaný cíl nebo cíle. To umožňuje autorovi projektu rozšířit existující sady cíle beze změny je přímo. Další informace najdete v tématu [cíl sestavení pořadí](../msbuild/target-build-order.md).|  
|`DependsOnTargets`|Nepovinný atribut.<br /><br /> Může dojít, cíle, které musí být provedeny, aby bylo možné spustit tento cíl nebo detekci nejvyšší úrovně závislosti. Více cílů oddělených středníky.|  
|`Label`|Nepovinný atribut.<br /><br /> Identifikátor, který můžete určit nebo pořadí elementů systému a uživatele.|  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Úloha](../msbuild/task-element-msbuild.md)|Vytvoří a spustí instanci [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úloh. Cílem může být nula nebo více úloh.|  
|[PropertyGroup –](../msbuild/propertygroup-element-msbuild.md)|Obsahuje sadu uživatelem definované `Property` elementy. Od verze rozhraní .NET Framework 3.5 `Target` element může obsahovat `PropertyGroup` elementy.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Obsahuje sadu uživatelem definované `Item` elementy. Od verze rozhraní .NET Framework 3.5 `Target` element může obsahovat `ItemGroup` elementy. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).|  
|[OnError](../msbuild/onerror-element-msbuild.md)|Způsobí, že jeden nebo více cílů, které mají spustit, pokud `ContinueOnError` atribut je ErrorAndStop (nebo `false`) pro nezdařené úlohy. Může být nula nebo více `OnError` elementů v cíl. Pokud `OnError` obsahují prvky, musí být poslední elementů v `Target` elementu.<br /><br /> Informace o `ContinueOnError` atributů najdete v tématu [Task – Element (MSBuild)](../msbuild/task-element-msbuild.md).|  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.|  

## <a name="remarks"></a>Poznámky  
 V době běhu je zadán prvního cíle k provedení. Cíle může mít závislosti na jiné cíle. Cíl pro nasazení, například závisí na cíl pro kompilaci. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Modul provádí v pořadí, ve kterém se zobrazí v závislosti `DependsOnTargets` atribut zleva doprava. Další informace najdete v tématu [cíle](../msbuild/msbuild-targets.md).  

 Cíl je spustit pouze jednou během sestavení, i v případě, že více než jeden cíl má závislost na.  

 Pokud cíl bylo přeskočeno, protože jeho `Condition` vyhodnocen jako atribut `false`, ho můžete stále provést, pokud je volána, později v sestavení a jeho `Condition` vyhodnocen jako atribut `true` v daném čase.  

 Před MSBuild 4 `Target` vrátí všechny položky, které byly uvedený v `Outputs` atribut.  K tomuto účelu MSBuild museli zaznamenávat položky v případě, že je požadovali úlohy později v buildu. Kvůli žádný způsob, jak určit, které cíle měl výstupů, které by vyžadovaly volající MSBuild nahromadění všechny položky ze všech `Outputs` na všech vyvolat `Target`s. Tato realizace škálování problémy týkající se sestavení, která měla velké množství položek výstup.  

 Pokud uživatel zadá `Returns` na žádném `Target` element v projektu a potom pouze ty `Target`s, které mají `Returns` atribut zaznamenávat tyto položky.  

 A `Target` může obsahovat i `Outputs` atribut a `Returns` atribut.  `Outputs`se používá s `Inputs` k určení, zda je aktuální cíl. `Returns`, pokud existuje, přepíše hodnotu `Outputs` k určení, které položky se vrátí pro volající.  Pokud `Returns` není k dispozici, pak `Outputs` bude k dispozici pro volající s výjimkou v případě, že popsané výše.  

 Před MSBuild 4, kdykoli se nástroj `Target` zahrnuté několik odkazů na stejné položky v jeho `Outputs`, by se zaznamenávat tyto duplicitní položky. Ve velmi velkých sestavení, který měl velký počet výstupů a mnoho vzájemné závislosti projektu, by vznikl velký objem paměti dojít ke znehodnocení části, protože duplicitní položky nebyly žádné použití. Když `KeepDuplicateOutputs` je atribut nastaven na `true`, zaznamenávají tyto duplikáty.  

## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `Target` element, který provede `Csc` úloh.  

```xml  
<Target Name="Compile" DependsOnTargets="Resources" Returns="$(TargetPath)">  
    <Csc Sources="@(CSFile)"  
          TargetType="library"  
          Resources="@(CompiledResources)"  
          EmitDebugInformation="$(includeDebugInformation)"  
          References="@(Reference)"  
          DebugType="$(debuggingType)" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
    </Csc>  
</Target>  
```  

## <a name="see-also"></a>Viz také  
 [Cíle](../msbuild/msbuild-targets.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)

---
title: "Project – Element (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Project
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ToolsVersion attribute [MSBuild]
- <Project> element [MSBuild]
- Project element [MSBuild]
ms.assetid: d1cda56a-dbef-4109-9201-39e962e3f653
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bf347f135368b2452170e7ebfa9c987ed19adf77
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="project-element-msbuild"></a>Project – element (MSBuild)
Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.  

## <a name="syntax"></a>Syntaxe  

```  
<Project InitialTargets="TargetA;TargetB"  
         DefaultTargets="TargetC;TargetD"  
         TreatAsLocalProperty="PropertyA;PropertyB"  
         ToolsVersion=<version number>
         Sdk="name[/version]"
         xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Sdk... />
    <Choose>... </Choose>  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <Target>... </Target>  
    <UsingTask.../>  
    <ProjectExtensions>... </ProjectExtensions>  
    <Import... />  
</Project>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`DefaultTargets`|Nepovinný atribut.<br /><br /> Výchozí cíl nebo cíle jako vstupní bod sestavení, pokud nebyl zadán žádný cíl. Více cílů se oddělte středníkem (;) oddělený.<br /><br /> Pokud není zadán žádný výchozí cíl buď `DefaultTargets` atribut nebo [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] příkazového řádku, modul provede první cíl v souboru projektu po [Import](../msbuild/import-element-msbuild.md) byly vyhodnoceny elementy.|  
|`InitialTargets`|Nepovinný atribut.<br /><br /> Počáteční cíl nebo cíle, které se má spustit před spuštěním cíle zadané v `DefaultTargets` atribut nebo na příkazovém řádku. Více cílů se oddělte středníkem (;) oddělený.|  
|`Sdk`|Nepovinný atribut. <br /><br /> Název sady SDK a volitelné verze se má použít k vytvoření implicitní importovat příkazy, které jsou přidány do souboru .proj. Pokud není určená verze, MSBuild pokusí přeložit výchozí verze.  Například `<Project Sdk="Microsoft.NET.Sdk" />` nebo `<Project Sdk="My.Custom.Sdk/1.0.0" />`.|  
|`ToolsVersion`|Nepovinný atribut.<br /><br /> Verze sady nástrojů MSBuild používá k určení hodnoty $(MSBuildBinPath) a $(MSBuildToolsPath).|  
|`TreatAsLocalProperty`|Nepovinný atribut.<br /><br /> Názvy vlastností, které nebude se zvažovat globální. Tento atribut zabrání přepsání hodnoty vlastností, které jsou nastavené v souboru projektu nebo cílů a všechny následné importy konkrétní vlastnosti příkazového řádku. Více vlastností jsou oddělte středníkem (;) oddělený.<br /><br /> Za normálních okolností vlastnosti globálních přepsat hodnoty vlastností, které jsou nastavené v souboru projektu nebo cíle. Pokud je vlastnost uveden `TreatAsLocalProperty` hodnotu, hodnotu globální vlastnosti není přepsat hodnoty vlastností, které jsou nastavené v souboru a všechny následné importy. Další informace najdete v tématu [postupy: sestavení stejných zdrojových souborů s různými možnostmi](../msbuild/how-to-build-the-same-source-files-with-different-options.md). **Poznámka:** nastavit globální vlastnosti na příkazovém řádku s použitím **/property** (nebo **/p**) přepínače. Můžete také nastavit nebo upravit vlastnosti globálních pro podřízené projektů v sestavení vícenásobného projektu pomocí `Properties` atribut úlohy nástroje MSBuild. Další informace najdete v tématu [úlohy nástroje MSBuild](../msbuild/msbuild-task.md).|  
|`Xmlns`|Nepovinný atribut.<br /><br /> -Li zadána, `xmlns` atributu musí mít hodnotu "http://schemas.microsoft.com/developer/msbuild/2003".|  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Zvolte](../msbuild/choose-element-msbuild.md)|Volitelný element.<br /><br /> Vyhodnotí podřízené elementy a vyberte jednu sadu `ItemGroup` elementy nebo `PropertyGroup` elementy k vyhodnocení.|  
|[Import](../msbuild/import-element-msbuild.md)|Volitelný element.<br /><br /> Umožňuje projektu soubor k importu jiný soubor projektu. Může být nula nebo více `Import` elementy v projektu.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Volitelný element.<br /><br /> Element seskupení pro jednotlivé položky. Položky, které jsou určeny pomocí [položky](../msbuild/item-element-msbuild.md) elementu. Může být nula nebo více `ItemGroup` elementy v projektu.|  
|[ProjectExtensions](../msbuild/projectextensions-element-msbuild.md)|Volitelný element.<br /><br /> Poskytuje způsob, jak zachovat jinou hodnotu než[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] informace v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu. Může být nula nebo jeden `ProjectExtensions` elementy v projektu.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Volitelný element.<br /><br /> Element seskupení pro jednotlivé vlastnosti. Vlastnosti jsou určeny pomocí [vlastnost](../msbuild/property-element-msbuild.md) elementu. Může být nula nebo více `PropertyGroup` elementy v projektu.|
|[Sdk](../msbuild/sdk-element-msbuild.md)|Volitelný element.<br /><br /> Odkazy [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu sady SDK.  Tento element slouží jako alternativu k atribut Sdk.|  
|[Cíl](../msbuild/target-element-msbuild.md)|Volitelný element.<br /><br /> Obsahuje sadu úloh pro [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] postupně provést. Úlohy zadávají pomocí [úloh](../msbuild/task-element-msbuild.md) elementu. Může být nula nebo více `Target` elementy v projektu.|  
|[Usingtask –](../msbuild/usingtask-element-msbuild.md)|Volitelný element.<br /><br /> Poskytuje způsob, jak zaregistrovat úlohy v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Může být nula nebo více `UsingTask` elementy v projektu.|  

### <a name="parent-elements"></a>Nadřazené elementy  
 Žádné  

## <a name="see-also"></a>Viz také  
 [Postupy: Zadejte, který prvního cíle k sestavení](../msbuild/how-to-specify-which-target-to-build-first.md)   
 [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)

---
title: Project – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 03/13/2017
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 598e802f9868399073bba7a6f1bc1f2278af83f6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54921043"
---
# <a name="project-element-msbuild"></a>Project – element (MSBuild)
Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.  

## <a name="syntax"></a>Syntaxe  

```xml  
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

| Atribut | Popis |
|------------------------| - |
| `DefaultTargets` | Nepovinný atribut.<br /><br /> Výchozí cíl nebo cíle se vstupním bodem sestavení, pokud nebyl zadán žádný cíl. Více cílů se středníkem (;) s oddělovači.<br /><br /> Pokud není zadána žádná výchozí cíl buď `DefaultTargets` atribut nebo [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] příkazového řádku, modul spustí první cíl v souboru projektu po [Import](../msbuild/import-element-msbuild.md) vyhodnocení elementy. |
| `InitialTargets` | Nepovinný atribut.<br /><br /> Počáteční cíle nebo cílů se má spustit před cíle zadané v `DefaultTargets` atribut nebo na příkazovém řádku. Více cílů se středníkem (`;`) s oddělovači. Pokud definujete více importovaných souborů `InitialTargets`, spustí se všechny cíle uvedené, v pořadí, v příkazu imports vyskytují. |
| `Sdk` | Nepovinný atribut. <br /><br /> Název sady SDK a volitelné verze, kterou chcete použít k vytvoření implicitní Import příkazy, které jsou přidány do souboru souborů .proj. Pokud není zadaná žádná verze, nástroj MSBuild se pokusí přeložit výchozí verze.  Například `<Project Sdk="Microsoft.NET.Sdk" />` nebo `<Project Sdk="My.Custom.Sdk/1.0.0" />`. |
| `ToolsVersion` | Nepovinný atribut.<br /><br /> Verze sady nástrojů MSBuild používá k určení hodnoty $(MSBuildBinPath) a $(MSBuildToolsPath). |
| `TreatAsLocalProperty` | Nepovinný atribut.<br /><br /> Názvy vlastností, které se za globální. Tento atribut zabrání přepsání hodnoty vlastností, které jsou nastaveny v souboru projektu nebo cílů a všechny následné importy specifické vlastnosti příkazového řádku. Víc vlastností se středníkem (;) s oddělovači.<br /><br /> Za normálních okolností se globální vlastnosti přepisují hodnoty vlastností, které jsou nastaveny v souboru projektu nebo cílů. Pokud vlastnost je uvedená v `TreatAsLocalProperty` hodnota nepřepíše hodnota globální vlastnosti hodnoty vlastností, které jsou nastaveny v souboru a všechny následné importy. Další informace najdete v tématu [jak: Sestavení stejných zdrojových souborů s různými možnostmi](../msbuild/how-to-build-the-same-source-files-with-different-options.md). **Poznámka:**  Nastavení globální vlastnosti příkazového řádku s použitím **– vlastnost** (nebo **-p**) přepnutí. Můžete také nastavit nebo upravit globální vlastnosti pro podřízené projekty v sestaveních s více projekty pomocí `Properties` atribut úlohy nástroje MSBuild. Další informace najdete v tématu [úlohy nástroje MSBuild](../msbuild/msbuild-task.md). |
| `Xmlns` | Nepovinný atribut.<br /><br /> -Li zadána, `xmlns` atribut musí mít hodnotu `http://schemas.microsoft.com/developer/msbuild/2003`. |

### <a name="child-elements"></a>Podřízené prvky  

| Prvek | Popis |
| - | - |
| [Choose](../msbuild/choose-element-msbuild.md) | Volitelný element.<br /><br /> Vyhodnotí jako podřízené prvky k výběru jedné sadě `ItemGroup` elementy a/nebo `PropertyGroup` prvky k vyhodnocení. |
| [Import](../msbuild/import-element-msbuild.md) | Volitelný element.<br /><br /> Umožňuje projektu soubor k importu jiný soubor projektu. Může být nula nebo více `Import` prvky v projektu. |
| [ImportGroup](../msbuild/importgroup-element.md) | Volitelný element.<br /><br /> Obsahuje kolekci `Import` prvky, které jsou seskupeny podle nepovinnou podmínku. |
| [ItemGroup](../msbuild/itemgroup-element-msbuild.md) | Volitelný element.<br /><br /> Element grouping pro jednotlivé položky. Položkami zadávají pomocí [položky](../msbuild/item-element-msbuild.md) elementu. Může být nula nebo více `ItemGroup` prvky v projektu. |
| [ItemDefinitionGroup](../msbuild/itemdefinitiongroup-element-msbuild.md) | Volitelný element.<br /><br /> Umožňuje definovat sadu definice položek, které jsou hodnoty metadat, které se použijí u všech položek v projektu, ve výchozím nastavení. ItemDefinitionGroup – nahrazuje nutnost používat `CreateItem` úloh a `CreateProperty` úloh. |
| [ProjectExtensions](../msbuild/projectextensions-element-msbuild.md) | Volitelný element.<br /><br /> Poskytuje způsob, jak zachovat jinou hodnotu než[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] informace [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu. Může být žádný nebo jeden `ProjectExtensions` prvky v projektu. |
| [PropertyGroup](../msbuild/propertygroup-element-msbuild.md) | Volitelný element.<br /><br /> Element grouping pro jednotlivé vlastnosti. Vlastnosti jsou určeny pomocí [vlastnost](../msbuild/property-element-msbuild.md) elementu. Může být nula nebo více `PropertyGroup` prvky v projektu. |
| [Sdk](../msbuild/sdk-element-msbuild.md) | Volitelný element.<br /><br /> Odkazy [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu sady SDK.  Tento element lze použít jako alternativu k atributu Sdk. |
| [Cíl](../msbuild/target-element-msbuild.md) | Volitelný element.<br /><br /> Obsahuje sadu úkolů pro [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] postupně provést. Úlohy je určené vlastností [úloh](../msbuild/task-element-msbuild.md) elementu. Může být nula nebo více `Target` prvky v projektu. |
| [Usingtask –](../msbuild/usingtask-element-msbuild.md) | Volitelný element.<br /><br /> Poskytuje způsob, jak zaregistrovat úlohy v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Může být nula nebo více `UsingTask` prvky v projektu. |

### <a name="parent-elements"></a>Nadřazené prvky  
 Žádné  

## <a name="see-also"></a>Viz také:  
 [Postupy: Zadejte cíl, které nejdřív sestavit](../msbuild/how-to-specify-which-target-to-build-first.md)   
 [Odkaz na příkazový řádek](../msbuild/msbuild-command-line-reference.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)

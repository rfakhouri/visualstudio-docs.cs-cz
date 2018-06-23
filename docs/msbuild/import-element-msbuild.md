---
title: Import – Element (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Import
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Import element [MSBuild]
- <Import> element [MSBuild]
ms.assetid: 3bfecaf1-69fd-4008-b651-c9dafd4389d9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 431184d2d4c2bf0bff5d6d3f4d5c44b3c6a670a2
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326962"
---
# <a name="import-element-msbuild"></a>Import – element (MSBuild)
Importuje obsah z jednoho souboru projektu do jiného souboru projektu.  

 \<Project>  
 \<Import >  

## <a name="syntax"></a>Syntaxe  

```xml  
<Import Project="ProjectPath"  
    Condition="'String A'=='String B'" />  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Project`|Požadovaný atribut.<br /><br /> Cesta souboru projektu k importu. Cestu můžete použít zástupné znaky. Odpovídající soubory importují seřazená. Pomocí této funkce můžete přidat kód do projektu právě přidáním souboru kódu do adresáře.|  
|`Condition`|Nepovinný atribut.<br /><br /> Stav, který se má vyhodnotit. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Podřízené elementy  
 Žádné  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.|  
|[ImportGroup](../msbuild/importgroup-element.md)|Obsahuje kolekci `Import` elementy seskupené v rámci nepovinnou podmínku.|  

## <a name="remarks"></a>Poznámky  
 Pomocí `Import` elementu, můžete opakovaně použít kód, který je společný pro mnoho souborů projektu. Díky tomu je snadněji provádět údržbu kód, protože všechny aktualizace, které můžete provést sdíleného kódu získat rozšířen na všechny projekty, které ji importovat.  

 Podle konvence sdílený projekt importované soubory ukládají jako soubory .targets, ale jsou standardní [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubory projektu. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] není zabránit vám v projektu, který má příponu názvu jiný soubor importu, ale doporučujeme použít rozšíření .targets konzistence.  

 Relativní cesty v importovaných projekty se interpretují relativní k adresáři Import projektu. Proto pokud soubor projektu je importovat do několika souborů projektu v různých umístěních, relativní cesty v souboru projektu importované, bude vyhodnocen odlišně pro každý importovaný projekt.  

 Všechny [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] rezervované vlastnosti, které se vztahují k souboru projektu, například `MSBuildProjectDirectory` a `MSBuildProjectFile`, který se odkazuje v importovaných projektu přiřazené hodnoty podle import souboru projektu.  

 Není-li importované projektu `DefaultTargets` atribut importovat projekty jsou prověřovány v pořadí, ve kterém jsou importované, a hodnota první zjištěny `DefaultTargets` je použit atribut. Například, pokud ProjectA importuje ProjectB a ProjectC (v tomto pořadí), a ProjectB importuje ProjectD [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] nejprve hledá `DefaultTargets` zadané v ProjectA, pak ProjectB, pak ProjectD a nakonec ProjectC.  

 Schéma importované projektu je stejná jako standardní projektu. I když [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pravděpodobně moci sestavení projektu importované, nepravděpodobné, protože importované projektu obvykle neobsahuje informace o vlastnosti, které chcete sadu nebo pořadí, ve kterém se má spouštět cíle. Importovaný projekt závisí na projekt, do kterého se importuje poskytnout tyto informace.  

> [!NOTE]
>  Zatímco příkazy pro import podmíněného pracovat v MSBuilds příkazového řádku, nepracují pomocí nástroje MSBuild v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Podmíněné importy vyhodnocují se pomocí hodnoty konfigurace a platformy, které jsou nastaveny při načtení projektu. Pokud následně změny vyžadující přehodnocení podmíněné příkazy v souboru projektu, například změna platformy, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] reevaluates podmínky na vlastností a položek, ale ne na import. Import bylo přeskočeno, protože již není znovu podmíněného import.  
>   
>  Chcete-li tento problém obejít, put podmíněného importy v souborech .targets nebo vložte kód podmíněného blok, jako [zvolte – Element (MSBuild)](../msbuild/choose-element-msbuild.md) bloku.  

## <a name="wildcards"></a>Zástupné znaky  
 V rozhraní .NET Framework 4 nástroje MSBuild umožňuje zástupné znaky v atributu projektu. Po zástupné znaky se všechny shody nalezen řadit (pro reprodukovatelnost) a poté jsou importované v tomto pořadí jako v případě, že pořadí byla explicitně nastaven.  

 To je užitečné, pokud chcete nabízet bod rozšiřitelnosti tak, aby někdo jiný můžete importovat soubor, aniž by bylo potřeba explicitně přidat název souboru pro import souboru. Pro tento účel Microsoft.Common.Targets obsahuje tento řádek v horní části souboru.  

```xml  
<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\$(MSBuildThisFile)\ImportBefore\*" Condition="'$(ImportByWildcardBeforeMicrosoftCommonTargets)' == 'true' and exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\$(MSBuildThisFile)\ImportBefore')"/>  
```  

## <a name="example"></a>Příklad  
 Následující příklad ukazuje projekt, který má několik položek a vlastnosti a naimportuje soubor obecné projektu.  

```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  

    <PropertyGroup>  
        <resourcefile>Strings.resx</resourcefile>  

        <compiledresources>  
            $(O)\$(MSBuildProjectName).Strings.resources  
        </compiledresources>  
    </PropertyGroup>  

    <ItemGroup>  
        <CSFile Include="*.cs" />  

        <Reference Include="System" />  
        <Reference Include="System.Data" />  
    </ItemGroup>  

    <Import Project="$(CommonLocation)\General.targets" />  
</Project>  
```  

## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Postupy: Použití stejného cíle ve více souborech projektu](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md)

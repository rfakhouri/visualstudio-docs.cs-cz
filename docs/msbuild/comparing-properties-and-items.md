---
title: Porovnávání vlastností a položek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, msbuild properties
ms.assetid: b9da45ae-d6a6-4399-8628-397deed31486
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7b879a8c4767f87b15df4dab17291c6367fb6a91
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="comparing-properties-and-items"></a>Porovnávání vlastností a položek
Vlastnosti nástroje MSBuild a položky se používají k předávání informací do úlohy, vyhodnoťte podmínky a uložit hodnoty, které může být odkazováno v souboru projektu.  
  
-   Vlastnosti jsou páry název hodnota. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).  
  
-   Položky jsou objekty, které obvykle představují soubory. Položka objekty mohou být přidruženy metadata kolekce. Metadata jsou páry název hodnota. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).  
  
## <a name="scalars-and-vectors"></a>Skalárních hodnot a vektory  
 Vzhledem k vlastnosti nástroje MSBuild jsou páry název hodnota, které mají jenom jednu řetězcovou hodnotu, jsou často popsané jako *skalární*. Protože se typy položky nástroje MSBuild seznam položek, jsou často popsané jako *vektoru*. V praxi, ale vlastnosti může představovat více hodnot a typů položek může mít žádnou nebo jednu položky.  
  
### <a name="target-dependency-injection"></a>Vkládání závislostí cíl  
 Informace o tom, jak můžete vlastnosti představují více hodnot, zvažte běžný vzor používání pro přidání cíle do seznam cílů, které má být sestaven. Tento seznam je obvykle reprezentována hodnotu vlastnosti s cílové názvy oddělené středníky.  
  
```xml  
<PropertyGroup>  
    <BuildDependsOn>  
        BeforeBuild;  
        CoreBuild;  
        AfterBuild  
    </BuildDependsOn>  
</PropertyGroup>  
```  
  
 `BuildDependsOn` Vlastnost se obvykle používá jako argument cíl `DependsOnTargets` atribut efektivně jeho převodem na seznam položek. Tato vlastnost může být přepsána přidání cíle nebo chcete-li změnit pořadí zpracování cíl. Například  
  
```xml  
<PropertyGroup>  
    <BuildDependsOn>  
        $(BuildDependsOn);  
        CustomBuild;  
    </BuildDependsOn>  
</PropertyGroup>  
```  
  
 Přidá cíl CustomBuild do cílového seznamu, která poskytuje `BuildDependsOn` hodnota `BeforeBuild;CoreBuild;AfterBuild;CustomBuild`.  
  
 Od verze nástroje MSBuild 4.0, vkládání závislostí cíl je zastaralý. Použití `AfterTargets` a `BeforeTargets` atributy místo. Další informace najdete v tématu [cíl sestavení pořadí](../msbuild/target-build-order.md).  
  
### <a name="conversions-between-strings-and-item-lists"></a>Převody mezi řetězci a položek seznamů  
 MSBuild provede převod na a z typů položek a hodnotami řetězců podle potřeby. Pokud chcete zobrazit, jak seznam položek se může stát řetězcovou hodnotu, zvažte, co se stane, pokud je jako hodnotu vlastnosti nástroje MSBuild použit typ položky:  
  
```xml  
<ItemGroup>  
    <OutputDir Include="KeyFiles\;Certificates\" />  
  </ItemGroup>  
<PropertyGroup>  
    <OutputDirList>@(OutputDir)</OutputDirList>  
</PropertyGroup>  
```  
  
 Typ položky má OutputDir `Include` atributu s hodnotou "klíčového souboru\\; Certifikáty\\". MSBuild analyzuje tento řetězec do dvou položek: KeyFiles\ a certifikáty\\. Pokud typ položky OutputDir slouží jako hodnota vlastnosti OutputDirList, MSBuild převede nebo "vyrovná" typ položky do oddělených středníkem řetězec "klíčového souboru\\; Certifikáty\\".  
  
## <a name="properties-and-items-in-tasks"></a>Vlastnosti a položky v úlohách  
 Vlastnosti a položky se používají jako vstupy a výstupy do úlohy nástroje MSBuild. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).  
  
 Vlastnosti jsou předány na úkoly jako atributy. V úloze je ve vlastnosti nástroje MSBuild reprezentována typ vlastnosti, jehož hodnota může být převedena do a z řetězce. Typy podporovaných vlastností zahrnují `bool`, `char`, `DateTime`, `Decimal`, `Double`, `int`, `string`, a jakýkoli typ, který <xref:System.Convert.ChangeType%2A> může zpracovat.  
  
 Položky jsou předány na úkoly jako <xref:Microsoft.Build.Framework.ITaskItem> objekty. V rámci úlohy <xref:Microsoft.Build.Framework.ITaskItem.ItemSpec%2A> představuje hodnotu položky a <xref:Microsoft.Build.Framework.ITaskItem.GetMetadata%2A> načte jeho metadata.  
  
 Seznam položek typu položka může být předána jako pole `ITaskItem` objekty. Od verze rozhraní .NET Framework 3.5, položky můžete odebrat ze seznamu položek v cíl pomocí `Remove` atribut. Protože položky můžete odebrat ze seznamu položku, je možné pro typ položky k obsahují nulové položky. Pokud seznam položek je předán úlohu, měli zkontrolovat kód v úloze pro tuto možnost.  
  
## <a name="property-and-item-evaluation-order"></a>Vlastnost a pořadí vyhodnocení položky  
 Během zkušební fáze sestavení importovaných souborů jsou součástí sestavení v pořadí, ve kterém jsou zobrazeny. Vlastnosti a položky jsou definovány v tři předává v následujícím pořadí:  
  
-   Vlastnosti jsou definovány a upravovat v pořadí, ve kterém jsou zobrazeny.  
  
-   Definice položek jsou definováni a upravovat v pořadí, ve kterém jsou zobrazeny.  
  
-   Položky jsou definovány a upravovat v pořadí, ve kterém jsou zobrazeny.  
  
 Během provádění fáze sestavení vlastností a položek, které jsou definovány v rámci cíle jsou vyhodnocovány společně v jediné fázi v pořadí, ve kterém jsou zobrazeny.  
  
 Je to ale není úplné scénáře. Pokud je vlastnost, definice položky nebo položky definované, vyhodnotí se jeho hodnota. Vyhodnocení výrazu rozšíří řetězec, který určuje hodnotu. Řetězec rozšíření je závislé na fázi sestavení. Tady je podrobnější pořadí vyhodnocení vlastností a položek:  
  
-   Během zkušební fáze sestavení:  
  
    -   Vlastnosti jsou definovány a upravovat v pořadí, ve kterém jsou zobrazeny. Funkce vlastností provedení. Hodnoty vlastností v $(PropertyName) formuláře rozbaleny v rámci výrazy. Hodnota vlastnosti je nastavena na rozšířené výraz.  
  
    -   Definice položek jsou definováni a upravovat v pořadí, ve kterém jsou zobrazeny. Funkce vlastností se rozšířily již v rámci výrazy. Metadata hodnoty jsou nastaveny na rozšířené výrazy.  
  
    -   Typů položek, které jsou definované a upravovat v pořadí, ve kterém jsou zobrazeny. Hodnoty položek v @(ItemType) formuláře jsou rozšířit. Transformace položky jsou také rozšířit. Funkce vlastností a hodnoty se již rozšířily v rámci výrazy. Položka metadat a seznamů hodnoty jsou nastaveny na rozšířené výrazy.  
  
-   Během provádění fáze sestavení:  
  
    -   Vlastnosti a položky, které jsou definovány v rámci cíle jsou vyhodnocovány společně v pořadí, ve kterém jsou zobrazeny. Provedení funkce vlastností a hodnoty vlastností rozbaleny v rámci výrazy. Hodnoty položky a transformace položky jsou také rozšířit. Hodnoty vlastností, hodnoty typu položky a metadata hodnoty jsou nastavené na rozšířené výrazy.  
  
### <a name="subtle-effects-of-the-evaluation-order"></a>Jemně důsledky pořadí vyhodnocení  
 Ve fázi hodnocení sestavení vyhodnocení vlastnosti předchází vyhodnocení položky. Nicméně vlastnosti může mít hodnoty, které se zobrazují na závisí na hodnotách položky. Vezměte v úvahu následující skript.  
  
```xml  
<ItemGroup>  
    <KeyFile Include="KeyFile.cs">  
        <Version>1.0.0.3</Version>  
    </KeyFile>  
</ItemGroup>  
<PropertyGroup>  
    <KeyFileVersion>@(KeyFile->'%(Version)')</KeyFileVersion>  
</PropertyGroup>  
<Target Name="AfterBuild">  
    <Message Text="KeyFileVersion: $(KeyFileVersion)" />  
</Target>  
```  
  
 Provádění úlohy zpráva se zobrazí tato zpráva:  
  
```  
KeyFileVersion: 1.0.0.3  
```  
  
 Důvodem je, že hodnota `KeyFileVersion` je ve skutečnosti řetězec "@(KeyFile -> % (verze))". Položky a transformace položky nebyly rozšířit při vlastnost nejprve definování, proto `KeyFileVersion` vlastnost byla přiřazena hodnota řetězce unexpanded.  
  
 Během provádění fáze sestavení, při zpracování úlohy zpráv MSBuild rozšíří řetězec "@(KeyFile -> % (verze))" pro získání "1.0.0.3".  
  
 Všimněte si, že tato zpráva objeví i v případě, že byly skupiny položku a vlastnost vrátit v pořadí.  
  
 V druhém příkladu zvažte, co může dojít v případě vlastností a položek skupiny se nacházejí v rámci cíle:  
  
```xml  
<Target Name="AfterBuild">  
    <PropertyGroup>  
        <KeyFileVersion>@(KeyFile->'%(Version)')</KeyFileVersion>  
    </PropertyGroup>  
    <ItemGroup>  
        <KeyFile Include="KeyFile.cs">  
            <Version>1.0.0.3</Version>  
        </KeyFile>  
    </ItemGroup>  
    <Message Text="KeyFileVersion: $(KeyFileVersion)" />  
</Target>  
```  
  
 Úloha zprávy zobrazí tato zpráva:  
  
```  
KeyFileVersion:   
```  
  
 Důvodem je, že během provádění fáze sestavení, vlastnosti a položku skupiny definované v rámci cíle vyhodnocují shora dolů ve stejnou dobu. Když `KeyFileVersion` je definován `KeyFile` neznámý. Proto transformace položky rozšíří na prázdný řetězec.  
  
 V takovém případě obrácení směru skupin položku a vlastnost obnoví původní zprávy:  
  
```xml  
<Target Name="AfterBuild">  
    <ItemGroup>  
        <KeyFile Include="KeyFile.cs">  
            <Version>1.0.0.3</Version>  
        </KeyFile>  
    </ItemGroup>  
    <PropertyGroup>  
        <KeyFileVersion>@(KeyFile->'%(Version)')</KeyFileVersion>  
    </PropertyGroup>  
    <Message Text="KeyFileVersion: $(KeyFileVersion)" />  
</Target>  
```  
  
 Hodnota `KeyFileVersion` na hodnotu "1.0.0.3" a nikoli k "@(KeyFile -> % (verze))". Úloha zprávy zobrazí tato zpráva:  
  
```  
KeyFileVersion: 1.0.0.3  
```  
  
## <a name="see-also"></a>Viz také  
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)
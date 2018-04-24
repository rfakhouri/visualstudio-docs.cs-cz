---
title: Metadata položek v dávkování cíle | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, target batching
- target batching [MSBuild]
ms.assetid: f3cc4186-6a4c-4161-bbe5-1ec638b4925b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e512ad9f932e34a6ddd95e165b116465aa359a09
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="item-metadata-in-target-batching"></a>Metadata položek v dávkování cíle
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] má schopnost provádět analýzy závislost na vstupy a výstupy cíl sestavení. Pokud je zjištěno, že vstupní nebo výstupní cíle jsou aktuální, cíl budou přeskočeny, a sestavení bude pokračovat. `Target` použít prvky `Inputs` a `Outputs` atributy a určete položky, chcete-li prověřit během analýzy závislostí.  
  
 Pokud obsahuje úlohu, která používá dávkové položky jako vstupní nebo výstupní, cíl `Target` element cíle by měl používat dávkování v jeho `Inputs` nebo `Outputs` atributy povolit [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] tak, aby přeskočil dávky položky, které jsou již aktuální.  
  
## <a name="batching-targets"></a>Dávkování cíle  
 Následující příklad obsahuje seznam položek s názvem `Res` , je rozdělené do dvou dávek na základě `Culture` metadata položky. Každý z těchto dávky je předána do `AL` úkolu, který vytvoří výstupní sestavení pro každou dávku. Pomocí dávkování na `Outputs` atribut `Target` elementu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] můžete zjistit, jestli všechny jednotlivé dávky aktuální před spuštěním cíl. Bez použití dávkování cíle, oba dávky položky by spustit úlohy pokaždé, když cíl byla spuštěna.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Res Include="Strings.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Strings.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
        <Res Include="Menus.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Dialogs.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Dialogs.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
        <Res Include="Menus.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
    </ItemGroup>  
  
    <Target Name="Build"  
        Inputs="@(Res)"  
        Outputs="%(Culture)\MyApp.resources.dll">  
  
        <AL Resources="@(Res)"  
            TargetType="library"  
            OutputAssembly="%(Culture)\MyApp.resources.dll"  
  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přírůstkové sestavování](../msbuild/how-to-build-incrementally.md)   
 [Dávkování](../msbuild/msbuild-batching.md)   
 [Target – Element (MSBuild)](../msbuild/target-element-msbuild.md)   
 [Metadata položek v dávkování úloh](../msbuild/item-metadata-in-task-batching.md)
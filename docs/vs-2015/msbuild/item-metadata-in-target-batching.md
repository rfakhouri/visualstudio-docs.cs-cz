---
title: Metadata položek v dávkování cíle | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, target batching
- target batching [MSBuild]
ms.assetid: f3cc4186-6a4c-4161-bbe5-1ec638b4925b
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2d91e294165012bea3b1ac196011cf9908469a7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628039"
---
# <a name="item-metadata-in-target-batching"></a>Metadata položek v dávkování cíle
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Metadata položek v dávkování cíle](https://docs.microsoft.com/visualstudio/msbuild/item-metadata-in-target-batching).  
  
  
[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] má schopnost provádět analýzu závislostí na vstupy a výstupy cíle sestavení. Pokud je zjištěno, že vstupy nebo výstupy cíle jsou aktuální, přeskočí se cíl a sestavení bude pokračovat. `Target` použití elementů `Inputs` a `Outputs` atributů zadejte položky, které chcete zkontrolovat během analýzu závislostí.  
  
 Pokud cíl obsahuje úlohu, která využívá jako vstupy nebo výstupy, dávková položka `Target` element cíle by měl použití dávkování v jeho `Inputs` nebo `Outputs` atributy se mají povolit [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] přeskočit dávky položek, které jsou již aktuální.  
  
## <a name="batching-targets"></a>Dávkování cíle  
 Následující příklad obsahuje seznam položek s názvem `Res` , který je rozdělen do dvou dávek na základě `Culture` metadata položky. Každá z těchto dávky je předán `AL` úkol, který vytvoří výstup sestavení u každé dávky. S použitím dávkování na `Outputs` atribut `Target` elementu [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] můžete zjistit, jestli každý jednotlivých dávek aktuální před spuštěním cílové. Bez použití dávkování cíle, obě dávky položek by spustit úlohy pokaždé, když byl cíl spuštěn.  
  
```  
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
 [Dávkové zpracování](../msbuild/msbuild-batching.md)   
 [Target – Element (MSBuild)](../msbuild/target-element-msbuild.md)   
 [Metadata položek v dávkování úloh](../msbuild/item-metadata-in-task-batching.md)




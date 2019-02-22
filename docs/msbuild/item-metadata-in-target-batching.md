---
title: Metadata položek v dávkování cíle | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, target batching
- target batching [MSBuild]
ms.assetid: f3cc4186-6a4c-4161-bbe5-1ec638b4925b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ff9aa4cdc2e3a406b21aeccf5538bcbfdd6b4249
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56606313"
---
# <a name="item-metadata-in-target-batching"></a>Metadata položek v dávkování cíle
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] má schopnost provádět analýzu závislostí na vstupy a výstupy cíle sestavení. Pokud je zjištěno, že vstupy nebo výstupy cíle jsou aktuální, cíl se přeskočí a bude pokračovat sestavení. `Target` použití elementů `Inputs` a `Outputs` atributů zadejte položky, které chcete zkontrolovat během analýzu závislostí.

Pokud cíl obsahuje úlohu, která využívá jako vstupy nebo výstupy, dávková položka `Target` element cíle by měl použití dávkování v jeho `Inputs` nebo `Outputs` atributy se mají povolit [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] přeskočit dávky položek, které jsou již aktuální.

## <a name="batch-targets"></a>Cíle služby batch
Následující příklad obsahuje seznam položek s názvem `Res` , který je rozdělen do dvou dávek na základě `Culture` metadata položky. Každá z těchto dávky je předán `AL` úkol, který vytvoří výstup sestavení u každé dávky. S použitím dávkování na `Outputs` atribut `Target` elementu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] můžete zjistit, jestli každý jednotlivých dávek aktuální před spuštěním cílové. Bez použití dávkování cíle, obě dávky položek by spustit úlohy pokaždé, když byl cíl spuštěn.

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
            OutputAssembly="%(Culture)\MyApp.resources.dll">

    </Target>

</Project>
```

## <a name="see-also"></a>Viz také:
- [Postupy: Přírůstkové sestavování](../msbuild/how-to-build-incrementally.md)
- [Dávkování](../msbuild/msbuild-batching.md)
- [Target – element (MSBuild)](../msbuild/target-element-msbuild.md)
- [Metadata položek v dávkování úloh](../msbuild/item-metadata-in-task-batching.md)

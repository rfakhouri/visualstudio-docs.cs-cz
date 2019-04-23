---
title: 'Postupy: Vytváření a odebírání závislostí projektu'
ms.date: 06/21/2017
ms.topic: conceptual
f1_keywords:
- VS.ProjectDependenciesDlg
helpviewer_keywords:
- vs.build.projectdependencies
- project dependencies
- builds [Visual Studio], setting up
- project build configurations, dependencies
- dependencies, project
- projects [Visual Studio], dependencies
ms.assetid: e2a0a8ff-dae7-40a8-b774-b88aa5235183
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 14c31acc336818a8846d2ddf7981f64e045f68e8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60062149"
---
# <a name="how-to-create-and-remove-project-dependencies"></a>Postupy: Vytváření a odebírání závislostí projektu

Při sestavování řešení, které obsahuje více projektů, může být nezbytné k sestavení některých projektů nejprve, pro generování kódu, které používají jiné projekty. Projekt využívá spustitelný kód vygenerovaný touto jiného projektu, projektu, který generuje kód se označuje jako závislost projektu, který využívá kód projektu. Tyto vztahy závislostí lze definovat v **závislosti projektu** dialogové okno.

## <a name="to-assign-dependencies-to-projects"></a>K přiřazení závislostí do projektů

1. V **Průzkumníka řešení**, vyberte projekt.

2. Na **projektu** nabídce zvolte **závislosti projektu**.

    **Závislosti projektu** zobrazí se dialogové okno.

   > [!NOTE]
   > **Závislosti projektu** možnost dostupná jenom v řešení s více než jeden projekt.

3. Na **závislosti** kartu, vyberte projekt z **projektu** rozevírací nabídky.

4. V **závisí na** pole, zaškrtněte políčko jiný projekt, který musíte vytvořit předtím, než se tento projekt.

   Řešení se musí skládat z více než jeden projekt, než budete moct vytvořit závislosti projektu.

## <a name="to-remove-dependencies-from-projects"></a>Chcete-li odebrat závislosti z projektů

1. V **Průzkumníka řešení**, vyberte projekt.

2. Na **projektu** nabídce zvolte **závislosti projektu**.

     **Závislosti projektu** zobrazí se dialogové okno.

    > [!NOTE]
    > **Závislosti projektu** možnost dostupná jenom v řešení s více než jeden projekt.

3. Na **závislosti** kartu, vyberte projekt z **projektu** rozevírací nabídky.

4. V **závisí na** pole, zrušte zaškrtnutí políček vedle jiné projekty, které už nejsou závislosti tohoto projektu.

## <a name="see-also"></a>Viz také:

- [Sestavení a vyčištění projektů a řešení v sadě Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)
- [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)
- [Správa vlastností projektu a řešení](managing-project-and-solution-properties.md)
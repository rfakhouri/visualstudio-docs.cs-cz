---
title: 'Postupy: vytvoření základní 3D modelu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a0d97966-2df8-449b-a8cf-5a19684dc773
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6627bac92221d66bd2cc1ab32efe10d0588c3b7e
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745682"
---
# <a name="how-to-create-a-basic-3d-model"></a>Postupy: vytvoření základní 3D modelu

Tento článek ukazuje, jak vytvořit základní 3D modelu pomocí editoru modelu. Jsou popsané níže uvedených aktivit:

-   Přidání objektů do scény

-   Výběr řezy a okraje

-   Výběr překladu

-   Pomocí **Rozdělit vzhled** a **tvarování vzhled** nástroje

-   Pomocí **Triangulate** příkaz

## <a name="create-a-basic-3d-model"></a>Vytvoření základního 3D modelu
 Editor modelu můžete vytvářet a upravovat 3D modely a scény pro hry nebo aplikace. Následující kroky ukazují, jak vytvořit jednoduchý model 3D domu pomocí editoru modelu. Zjednodušený model slouží jako stand-in pro konečné obrázky prostředky, které jsou stále probíhá vytváření, jako mřížku pro detekce kolizí nebo nízké podrobností model má být použita, pokud objekt, který reprezentuje je příliš daleko abyste mohli využívat výhod vykreslování podrobnější.

 Jakmile budete hotovi, modelu by měl vypadat přibližně takto:

 ![Dokončené model zjednodušené úklidové](../designers/media/gfx_model_demo_house_final.png)

 Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

### <a name="to-create-a-simplified-3d-model-of-a-house"></a>Pro vytvoření modelu zjednodušené 3D domu

1.  Vytvořte 3D model pro práci s. Informace o tom, jak přidat model do projektu, najdete v části Začínáme v [modelu Editor](../designers/model-editor.md).

2.  Přidejte do scény datovou krychli. V **sada nástrojů** okno, v části **tvarů**, vyberte **datové krychle** a poté ho přesuňte na plochu návrháře.

3.  Umožňuje přepnout do vzhled výběru. Na panelu nástrojů editoru modelu zvolte **vyberte vzhled**.

4.  Rozdělit horní části datové krychle. V režimu výběru řez zvolte datové krychle jednou aktivace pro výběr a zvolte horní části datové krychle vyberte nejvyšší písmo. Na panelu nástrojů editoru modelu zvolte **Rozdělit vzhled**. Tento postup přidá novou vrcholy do horní části datové krychle, která rozdělená do čtyř oddílů stejně velké.

     ![Horní části datové krychle byly rozděleny.](../designers/media/gfx_model_demo_house_subdiv.png)

5.  Tvarování sociálními přiléhající datové krychle – například přední a pravé straně datové krychle. V režimu výběru řez zvolte datové krychle jednou aktivovat pro výběr a potom vyberte jedné straně datové krychle. Stiskněte a přidržte klávesu ovládací prvek, zvolte jiné straně sousedícího na straně, které jste vybrali nejprve datové krychle a na panelu nástrojů editoru modelu zvolte **tvarování vzhled**.

     ![Mít byla vyňaty postranní datové krychle](../designers/media/gfx_model_demo_house_extrude.png)

6.  Jeden z extrusions rozšiřte. Vyberte jednu z řezy, které jste právě vyňaty a potom na panelu nástrojů editoru modelu zvolte **přeložit** nástroje a přesunout manipulator překlad ve stejném směru jako vysunutí.

     ![Další má byla vyňaty jedné straně datové krychle.](../designers/media/gfx_model_demo_house_extend.png)

7.  Triangulovat modelu. Na panelu nástrojů editoru modelu zvolte **Upřesnit**, **nástroje**, **Triangulate**.

8.  Vytvořte stropu budovy. Přepnout na režim výběru edge tak, že zvolíte **vyberte okraj** na panelu nástrojů editoru modelu a potom vyberte datovou krychli aktivovat. Stiskněte a přidržte klávesu ovládací prvek, při výběru okrajů, které jsou zobrazeny zde:

     ![Okraje, které budou formovat ve špičce z stropu](../designers/media/gfx_model_demo_house_edges.png)

     Když jsou vybrané okrajů, na panelu nástrojů editoru modelu, vyberte **přeložit** nástroje a poté přesuňte manipulator překlad směrem nahoru k vytvoření stropu budovy.

 Zjednodušená úklidové modelu je dokončena. Tady je poslední model znovu s konstantní stínování použít:

 ![Dokončené model zjednodušené úklidové](../designers/media/gfx_model_demo_house_final.png)

 Jako další krok můžete použít shaderu k tomuto 3D modelu. Informace najdete v tématu [postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md).

## <a name="see-also"></a>Viz také:

- [Postupy: Model 3D geologické struktury](../designers/how-to-model-3-d-terrain.md)
- [Editor modelů](../designers/model-editor.md)
- [Návrhář shaderů](../designers/shader-designer.md)
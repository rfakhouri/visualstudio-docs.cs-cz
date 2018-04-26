---
title: 'Postupy: Vytvoření přechodu shaderu založeného na geometrii'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 4b204405-ba95-4c5e-bd51-ec033a3ebfb6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ab2aeea5cf70b3c9a70b9f8e80961825bfff179a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-geometry-based-gradient-shader"></a>Postupy: Vytvoření přechodu shaderu založeného na geometrii

Tento článek ukazuje, jak vytvořit na základě geometrie přechodu shaderu pomocí návrháře shaderu a jazyk směrované shaderu grafu. Tato shaderu škáluje konstantní hodnotu barva RGB podle výšky každého bodu objektu v prostoru world.

## <a name="create-a-geometry-based-gradient-shader"></a>Vytvořit na základě geometrie přechodu shaderu

Na základě geometrie shaderu můžete implementovat začleněním pozici pixelech do vaší shaderu. V jazyce stínování obsahuje jeden bod informace než jenom jeho barvy a umístění na 2D obrazovce. Jeden bod – označuje jako *fragment* v některé systémy – je kolekce hodnot, které popisují prostor, který odpovídá pixelu. Shaderu, který je popsaný v tomto dokumentu využívá výška jednotlivých pixelů 3D objektu v prostoru world ovlivnit barvu závěrečný výstup fragmentu.

Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

1.  Vytvořte DGSL shaderu pro práci s. Informace o tom, jak do projektu přidejte shaderu DGSL, najdete v části Začínáme v [shaderu Návrhář](../designers/shader-designer.md).

2.  Odpojení **bodu barva** uzlu z **konečnou barvu** uzlu. Vyberte **RGB** Terminálové služby **bodu barva** uzel a potom vyberte **rozdělit odkazy**. Díky tomu místnosti uzlu, který je přidán v dalším kroku.

3.  Přidat **násobení** uzel do grafu. V **sada nástrojů**v části **matematické**, vyberte **násobení** a přesunout ho na plochu návrháře.

4.  Přidat **maska vektoru** uzel do grafu. V **sada nástrojů**v části **nástroj**, vyberte **maska vektoru** a přesunout ho na plochu návrháře.

5.  Zadejte hodnoty masky pro **maska vektoru** uzlu. V **vyberte** režimu, vyberte **maska vektoru** uzel a potom v **vlastnosti** nastavte **zelená / Y** vlastnost **True**a poté nastavte **Red / X**, **modrá nebo Z** a **Alpha / W** vlastnosti, které chcete **False**. V tomto příkladu **Red / X**, **zelená / Y**, a **Blue nebo Z** vlastnosti odpovídají x, y a z různých součástí **World pozice** uzel, a **Alpha / W** se nepoužívá. Protože pouze **zelená / Y** je nastaven na **True**, pouze y komponenta vstupní vektoru zůstává poté, co je maskování.

6.  Přidat **World pozice** uzel do grafu. V **sada nástrojů**v části **konstanty**, vyberte **World pozice** a přesunout ho na plochu návrháře.

7.  Masku pozice místa na světě fragment. V **vyberte** režimu, přesunout **výstup** Terminálové služby **World pozice** uzlu **vektoru** Terminálové služby **maska Vektor** uzlu. Toto připojení zakrývá pozici fragment ignorovat x a z komponenty.

8.  Vynásobte konstanta barva RGB místo umístěním maskované world. Přesunout **RGB** Terminálové služby **barva bodu** uzlu **Y** Terminálové služby **násobení** uzel a poté ho přesuňte  **Výstup** Terminálové služby **maska vektoru** uzlu **X** Terminálové služby **násobení** uzlu. Toto připojení škáluje hodnoty barvy podle výšku pixelů v prostoru world.

9. Hodnota škálovat barvy se připojte k konečnou barvu. Přesunout **výstup** Terminálové služby **násobení** uzlu **RGB** Terminálové služby **konečnou barvu** uzlu.

Následující obrázek znázorňuje dokončené shaderu a náhled shaderu použít oblasti grafu.

> [!NOTE]
> V tomto obrázku oranžovou barvu je určena k lépe ukazují účinek shaderu, ale protože preview tvar, který má žádné pozici v prostoru world, shaderu nemůže zobrazit jejich náhled plně v Návrháři shaderu. Shaderu musí zobrazit náhled v skutečné scény k předvedení plný vliv.

 ![Graf shaderu a náhled jeho dopad](../designers/media/digit-gradient-effect-graph.png "číslice přechodu vliv grafu")

 Určité tvarů může poskytovat lepší verze Preview pro některé shadery. Informace o tom, jak zobrazit náhled shadery v Návrháři shaderu najdete v tématu **náhled shadery** v [shaderu návrháře](../designers/shader-designer.md)

 Následující obrázek znázorňuje shaderu, který je popsaný v tomto dokumentu použít pro 3D scény, která je znázorněna v [postup: Model 3D geologické struktury](../designers/how-to-model-3-d-terrain.md). Intenzita barvy se zvyšuje s výšky bodu v celém světě.

 ![Přechodu vliv u a 3&#45;D geologické struktury modelu](../designers/media/digit-gradient-effect-result.png "číslice přechodu vliv výsledek")

 Další informace o tom, jak používat shaderu 3D modelu najdete v tématu [postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md).

## <a name="see-also"></a>Viz také

- [Postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Postupy: Exportování shaderu](../designers/how-to-export-a-shader.md)
- [Postupy: Model 3D geologické struktury](../designers/how-to-model-3-d-terrain.md)
- [Postupy: Vytvoření shaderu textury stupňů šedé](../designers/how-to-create-a-grayscale-texture-shader.md)
- [Návrhář shaderů](../designers/shader-designer.md)
- [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)
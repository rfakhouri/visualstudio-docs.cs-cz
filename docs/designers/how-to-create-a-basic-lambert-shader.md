---
title: 'Postupy: Vytvoření základního Lambertova shaderu'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: ec5c10fb-9600-4240-8280-d59451ea1d68
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1a843f15275893f0c4ffe110e39bb2069b5a51be
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-basic-lambert-shader"></a>Postupy: Vytvoření základního Lambertova shaderu

Tento článek ukazuje, jak vytvořit shaderu osvětlení, který implementuje klasického modelu osvětlení společnost Lambert pomocí návrháře shaderu a jazyk shaderu grafu (DGSL) přesměruje.

## <a name="the-lambert-lighting-model"></a>Společnost Lambert osvětlení modelu

Model osvětlení společnost Lambert zahrnuje vedlejším a směrovou osvětlení stín objektů v 3D scény. Vedlejším komponenty poskytují základní úroveň světelného v 3D scény. Směrovou komponenty poskytují další osvětlení z směrovou (vzdálené) světla zdrojů. Vedlejším osvětlení ovlivňuje všechny plochy v scény stejným způsobem, bez ohledu na jejich orientaci. Pro daný prostor je produkt vedlejším barvu povrchu a barvy a intenzitou osvětlení okolí v scény. Směrovou osvětlení má vliv na každý prostor v scény odlišně, na základě orientace prostor s ohledem na směru světelného zdroje. Je produkt rozptýlených barvy a orientaci na povrch a barvu, intenzitou a směr zdrojů světla. Povrchy směřujících přímo směrem ke zdroji světla získat maximální příspěvek a povrchy směřujících přímo rychle získat žádné příspěvek. V rámci modelu osvětlení společnost Lambert komponentu vedlejším a jednu nebo více součástí směrovou slučují určit celkový rozptýlených barva příspěvku pro každý bod v objektu.

Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

1.  Vytvořte DGSL shaderu pro práci s. Informace o tom, jak do projektu přidejte shaderu DGSL, najdete v části Začínáme v [shaderu Návrhář](../designers/shader-designer.md).

2.  Odpojení **bodu barva** uzlu z **konečnou barvu** uzlu. Vyberte **RGB** Terminálové služby **bodu barva** uzel a potom vyberte **rozdělit odkazy**. Ponechte **Alpha** připojení terminál.

3.  Přidat **společnost Lambert** uzel do grafu. V **sada nástrojů**v části **nástroj**, vyberte **společnost Lambert** a přesunout ho na plochu návrháře. Uzel společnost lambert vypočítá příspěvek celkový rozptýlených barev pixelů, na základě vedlejším a rozptýlené osvětlení parametrů.

4.  Připojení **bodu barva** uzlu **společnost Lambert** uzlu. V **vyberte** režimu, přesunout **RGB** Terminálové služby **barva bodu** uzlu **rozptýlené barva** Terminálové služby **společnost Lambert**  uzlu. Toto připojení poskytuje společnost lambert uzlu rozptýlených interpolované barvou pixelech.

5.  Hodnota počítaného barvy se připojte k konečnou barvu. Přesunout **výstup** Terminálové služby **společnost Lambert** uzlu **RGB** Terminálové služby **konečnou barvu** uzlu.

 Následující obrázek znázorňuje dokončené shaderu graf a náhled shaderu použité pro teapot model.

> [!NOTE]
> K předvedení lépe účinku shaderu na tomto obrázku, byla zadána oranžovou barvu pomocí **MaterialDiffuse** parametr shaderu. Hry nebo aplikace můžete tento parametr slouží k poskytování hodnotu jedinečnou barvu pro každý objekt. Informace o parametrech podstatným, najdete v části Náhled shadery v [shaderu Návrhář](../designers/shader-designer.md).

 ![Graf shaderu a náhled jeho platnost. ] (../designers/media/digit-lambert-effect-graph.png "Číslice společnost Lambert vliv grafu")

 Určité tvarů může poskytovat lepší verze Preview pro některé shadery. Další informace o tom, jak zobrazit náhled shadery v Návrháři shaderu, najdete v části Náhled shadery v [shaderu Návrhář](../designers/shader-designer.md).

 Následující obrázek znázorňuje shaderu, který je popsaný v tomto dokumentu použít pro 3D model.

 ![Společnost Lambert osvětlení použít pro model. ] (../designers/media/digit-lambert-effect-result.png "Číslice společnost Lambert vliv výsledek")

 Další informace o tom, jak používat shaderu 3D modelu najdete v tématu [postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md).

## <a name="see-also"></a>Viz také

- [Postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Postupy: Exportování shaderu](../designers/how-to-export-a-shader.md)
- [Postupy: Vytvoření základního Phongova shaderu](../designers/how-to-create-a-basic-phong-shader.md)
- [Návrhář shaderů](../designers/shader-designer.md)
- [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)
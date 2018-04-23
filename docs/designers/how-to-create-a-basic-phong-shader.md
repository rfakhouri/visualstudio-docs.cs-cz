---
title: 'Postupy: Vytvoření základního Phongova shaderu'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: c7c69da8-142b-4d3b-9be9-4be0d5970b25
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f81d6e34a6fe0932a8bccae2202c1640b8befb76
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-basic-phong-shader"></a>Postupy: Vytvoření základního Phongova shaderu

Tento článek ukazuje, jak vytvořit shaderu osvětlení, který implementuje klasického modelu osvětlení Phong pomocí návrháře shaderu a jazyk shaderu grafu (DGSL) přesměruje.

## <a name="the-phong-lighting-model"></a>Model osvětlení Phong

Model osvětlení Phong rozšiřuje možnosti společnost Lambert osvětlení zahrnout zrcadlová zvýraznění, který simuluje odrážející vlastnosti prostor. Zrcadlová součást poskytuje další osvětlení ze stejného směrovou světla zdroje, které se používají v modelu osvětlení společnost Lambert, ale jeho příspěvku konečnou barvu zpracování jinak. Zrcadlová zvýraznění má vliv na každý prostor v scény odlišně, na základě vztahu mezi směr zobrazení, směr zdroje světla a orientaci na povrch. Je produkt zrcadlová barvu, zrcadlová napájení a orientaci na povrch a barvu, intenzitou a směr zdrojů světla. Povrchy, které odráží ke zdroji světla přímo v prohlížeči zobrazí maximální zrcadlová příspěvku a povrchy, které odráží ke zdroji světla mimo prohlížeč získat žádné příspěvek. V rámci modelu osvětlení Phong jeden nebo více zrcadlová součásti se zkombinují k určení, barvu a intenzitou zrcadlová zvýraznění pro každý bod v objektu a potom se přidají do výsledek modelu osvětlení společnost Lambert a vytvoření konečné barev obrazového bodu .

Další informace o modelu osvětlení společnost Lambert najdete v tématu [postupy: vytvoření základní shaderu společnost Lambert](../designers/how-to-create-a-basic-lambert-shader.md).

Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

1.  Vytvořit společnost Lambert shaderu, jak je popsáno v [postupy: vytvoření základní shaderu společnost Lambert](../designers/how-to-create-a-basic-lambert-shader.md).

2.  Odpojení **společnost Lambert** uzlu z **konečnou barvu** uzlu. Vyberte **RGB** Terminálové služby **společnost Lambert** uzel a potom zvolte **rozdělit odkazy**. Díky tomu místnosti uzlu, který je přidán v dalším kroku.

3.  Přidat **přidat** uzel do grafu. V **sada nástrojů**v části **matematické**, vyberte **přidat** a přesunout ho na plochu návrháře.

4.  Přidat **Specular** uzel do grafu. V **sada nástrojů**v části **nástroj**, vyberte **Specular** a přesunout ho na plochu návrháře.

5.  Přidejte zrcadlová příspěvku. Přesunout **výstup** Terminálové služby **Specular** uzlu **X** Terminálové služby **přidat** uzel a poté ho přesuňte **výstup**  Terminálové služby **společnost Lambert** uzlu **Y** Terminálové služby **přidat** uzlu. Tato připojení kombinovat příspěvky celkový rozptýlených a zrcadlová barvu pro pixelech.

6.  Hodnota počítaného barvy se připojte k konečnou barvu. Přesunout **výstup** Terminálové služby **přidat** uzlu **RGB** Terminálové služby **konečnou barvu** uzlu.

 Následující obrázek znázorňuje dokončené shaderu graf a náhled shaderu použité pro teapot model.

> [!NOTE]
> K předvedení lépe účinku shaderu na tomto obrázku, byla zadána oranžovou barvu pomocí **MaterialDiffuse** je zadán parametr shaderu a dokončit se kovovým vyhledávání pomocí **MaterialSpecular** a **MaterialSpecularPower** parametry. Informace o parametrech podstatným, najdete v části Náhled shadery v [shaderu Návrhář](../designers/shader-designer.md).

 ![Graf shaderu a náhled jeho dopad](../designers/media/digit-lighting-graph.png "číslice. osvětlení grafu")

 Určité tvarů může poskytovat lepší verze Preview pro některé shadery. Další informace o tom, jak zobrazit náhled shadery v Návrháři shaderu, najdete v části Náhled shadery v [shaderu návrháře](../designers/shader-designer.md)

 Následující obrázek znázorňuje shaderu, který je popsaný v tomto dokumentu použít pro 3D model. **MaterialSpecular** je nastavena na (1,00, 0,50, 0,20, 0,00) a jeho **MaterialSpecularPower** je nastavena na 16.

> [!NOTE]
> **MaterialSpecular** vlastnost určuje zřejmá dokončit prostor materiálu. Vysoce optimalizovaného prostor například skla nebo plastu obvykle mají zrcadlová barvu, která je jasně odstín bílé. Kovovém povrchu obvykle mají zrcadlová barvu, která je blízko jeho rozptýlených barev. Prostor Satén dokončit obvykle mají zrcadlová barvu, která je tmavý odstín šedé.
>
> **MaterialSpecularPower** vlastnost určuje, jak velký zrcadlová světla. Zrcadlová zajišťuje vysokou simulovat méně výrazné, další lokalizované označuje. Velmi nízkou zrcadlová zajišťuje simulovat velký, obezřetností označuje, které se dají oversaturate a skrýt barva celou plochu.

 ![Použít pro model osvětlení Phong](../designers/media/digit-lighting-model.png "číslice. osvětlení modelu")

 Další informace o tom, jak používat shaderu 3D modelu najdete v tématu [postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md).

## <a name="see-also"></a>Viz také

- [Postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Postupy: Exportování shaderu](../designers/how-to-export-a-shader.md)
- [Postupy: Vytvoření základního Lambertova shaderu](../designers/how-to-create-a-basic-lambert-shader.md)
- [Návrhář shaderů](../designers/shader-designer.md)
- [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)
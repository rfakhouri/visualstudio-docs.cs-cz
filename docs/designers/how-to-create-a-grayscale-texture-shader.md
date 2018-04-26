---
title: 'Postupy: Vytvoření shaderu textury stupňů šedé'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 79181d81-44af-445e-9a18-03483dd70260
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f745033ecb88fd70de4c7150dc5ae3165ab3c99b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-grayscale-texture-shader"></a>Postupy: Vytvoření shaderu textury stupňů šedé

Tento článek ukazuje, jak vytvořit shaderu texture ve stupních šedi pomocí návrháře shaderu a jazyk shaderu grafu (DGSL) přesměruje. Tato shaderu upraví hodnoty barva RGB ukázka texture a používá je spolu s beze změny alfa nastavit konečnou barvu.

## <a name="create-a-grayscale-texture-shader"></a>Vytvořte ve stupních šedi texture shaderu

Texture shaderu ve stupních šedi můžete implementovat změnou hodnoty barvy ukázku texture před zápisem barvu závěrečný výstup.

Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

1.  Vytvořte základní texture shaderu, jak je popsáno v [postupy: vytvoření základní shaderu Texture](../designers/how-to-create-a-basic-texture-shader.md).

2.  Odpojit **RGB** Terminálové služby **ukázka Texture** uzlu z **RGB** Terminálové služby **konečnou barvu** uzlu. V **vyberte** režimu, vyberte **RGB** Terminálové služby **ukázka Texture** uzel a potom vyberte **rozdělit odkazy**. Díky tomu místnosti uzlu, který je přidán v dalším kroku.

3.  Přidat **Odbarvit** uzel do grafu. V **sada nástrojů**v části **filtry**, vyberte **Odbarvit** a přesunout ho na plochu návrháře.

4.  Výpočet hodnota ve stupních šedi pomocí **Odbarvit** uzlu. V **vyberte** režimu přesunout **RGB** Terminálové služby **Texture ukázkové** uzlu **RGB** Terminálové služby **Odbarvit**  uzlu.

    > [!NOTE]
    > Ve výchozím nastavení **Odbarvit** uzlu plně desaturates vstupní barva a používá standardní světlostí vah pro stupně šedi převod. Můžete změnit jak **Odbarvit** uzlu se chová tak, že změníte hodnotu **světlostí** vlastnost, nebo jen částečně desaturating vstupní barva. Chcete-li snížit částečně sytost vstupní barva, zadat skalární hodnotu v rozsahu [0,1) k **procent** Terminálové služby **Odbarvit** uzlu.

5.  Hodnota ve stupních šedi barvy se připojte k konečnou barvu. Přesunout **výstup** Terminálové služby **Odbarvit** uzlu **RGB** Terminálové služby **konečnou barvu** uzlu.

Následující obrázek znázorňuje dokončené shaderu graf a náhled shaderu použít na datovou krychli.

> [!NOTE]
> V tomto obrázku rovině slouží jako tvaru preview a texturou byla zadána lépe předvedení účinek shaderu.

![Graf shaderu a náhled jeho dopad](../designers/media/digit-grayscale-effect.png "číslice. ve stupních šedi vliv")

Určité tvarů může poskytovat lepší verze Preview pro některé shadery. Další informace o zobrazení náhledu shadery v Návrháři shaderu najdete v tématu [shaderu návrháře](../designers/shader-designer.md)

## <a name="see-also"></a>Viz také

- [Postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Postupy: Exportování shaderu](../designers/how-to-export-a-shader.md)
- [Editor obrázků](../designers/image-editor.md)
- [Návrhář shaderů](../designers/shader-designer.md)
- [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)
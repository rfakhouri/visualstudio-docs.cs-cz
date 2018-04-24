---
title: 'Postupy: Vytvoření shaderu základní textury'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 5af113fb-6415-4be0-8b23-10fddb10e80a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: efe0031eed40424dbe9dc0219ecf82c69e44b33c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-basic-texture-shader"></a>Postupy: Vytvoření shaderu základní textury

Tento článek ukazuje, jak vytvořit jeden texture shaderu pomocí návrháře shaderu a jazyk shaderu grafu (DGSL) přesměruje. Tato shaderu nastaví barvu konečné přímo na RGB a alfa hodnot, které jsou odebírána data z textury.

## <a name="create-a-basic-texture-shader"></a>Vytvořte základní texture shaderu

Základní, jedním texture shaderu můžete implementovat pomocí zápisu barvy a alfa hodnot ukázku texture přímo do barvu závěrečný výstup.

Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

1.  Vytvořte DGSL shaderu pro práci s. Informace o tom, jak do projektu přidejte shaderu DGSL, najdete v části Začínáme v [shaderu Návrhář](../designers/shader-designer.md).

2.  Odstranit **bodu barva** uzlu. V **vyberte** režimu, vyberte **bodu barva** uzel a potom na panelu nabídek vyberte **upravit**, **odstranit**. Díky tomu místnosti uzlu, který je přidán v dalším kroku.

3.  Přidat **ukázka Texture** uzel do grafu. V **sada nástrojů**v části **Texture**, vyberte **ukázka Texture** a přesunout ho na plochu návrháře.

4.  Přidat **koordinaci Texture** uzel do grafu. V **sada nástrojů**v části **Texture**, vyberte **koordinaci Texture** a přesunout ho na plochu návrháře.

5.  Zvolte texture použít. V **vyberte** režimu, vyberte **ukázka Texture** uzel a potom v **vlastnosti** okno, zadejte texture, který chcete používat pomocí **Filename**  vlastnost.

6.  Ujistěte se, textury veřejně přístupná. Vyberte **Texture ukázka** uzel a potom v **vlastnosti** nastavte **přístup** vlastnost **veřejné**. Teď textury můžete nastavit od jiného nástroje, jako **modelu Editor**.

7.  Připojte k ukázkové texture texture souřadnice. V **vyberte** režimu, přesunout **výstup** Terminálové služby **koordinaci Texture** uzlu **UV** Terminálové služby **Texture Ukázka** uzlu. Toto připojení ukázky texture v zadaných souřadnic.

8.  Ukázka texture se připojte k konečnou barvu. Přesunout **RGB** Terminálové služby **ukázka Texture** uzlu **RGB** Terminálové služby **konečnou barvu** uzel a poté ho přesuňte **Alpha** Terminálové služby **ukázka Texture** uzlu **Alpha** Terminálové služby **konečnou barvu** uzlu.

Následující obrázek znázorňuje dokončené shaderu graf a náhled shaderu použít na datovou krychli.

> [!NOTE]
> V tomto obrázku rovině slouží jako tvaru preview a texturou byla zadána lépe předvedení účinek shaderu.

![Graf shaderu a náhled jeho dopad](../designers/media/digit-texture-effect.png "číslice. Texture vliv")

Určité tvarů může poskytovat lepší verze Preview pro některé shadery. Další informace o tom, jak zobrazit náhled shadery v Návrháři shaderu najdete v tématu [shaderu návrháře](../designers/shader-designer.md)

## <a name="see-also"></a>Viz také

- [Postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Editor obrázků](../designers/image-editor.md)
- [Návrhář shaderů](../designers/shader-designer.md)
- [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)
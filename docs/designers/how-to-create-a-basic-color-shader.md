---
title: 'Postupy: Vytvoření shaderu základní barvy'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: c301328a-079a-49e8-b688-4749c01657c0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fba456d6a06281e0472e907b27bcd76b57b17e93
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747115"
---
# <a name="how-to-create-a-basic-color-shader"></a>Postupy: Vytvoření shaderu základní barvy

Tento článek ukazuje, jak vytvořit plochý barevný shaderu pomocí návrháře shaderu a jazyk shaderu grafu (DGSL) přesměruje. Tento shaderu nastaví barvu konečné na konstantní hodnotu barva RGB.

## <a name="create-a-flat-color-shader"></a>Vytvořit plochý barevný shaderu

Můžete implementovat plochý barevný shaderu zápisem barva hodnota konstanty barva RGB do barvu závěrečný výstup.

Než začnete, ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

1.  Vytvořte DGSL shaderu pro práci s. Informace o tom, jak do projektu přidejte shaderu DGSL, najdete v části Začínáme v [shaderu Návrhář](../designers/shader-designer.md).

2.  Odstranit **bodu barva** uzlu. Použití **vyberte** nástroj pro výběr **barva bodu** uzel a potom na panelu nabídek vyberte **upravit**, **odstranit**.

3.  Přidat **barva konstantní** uzel do grafu. V **sada nástrojů**v části **konstanty**, vyberte **barva konstantní** a přesunout ho na plochu návrháře.

4.  Zadejte hodnotu barva **barva konstantní** uzlu. Použití **vyberte** nástroj pro výběr **barva konstantní** uzlu a pak na **vlastnosti** okno v **výstup** vlastnost, zadejte Hodnota barvy. Oranžová zadejte hodnotu (1.0, 0,5, 0,2, 1.0).

5.  Barva konstanta se připojte k konečnou barvu. Chcete-li vytvořit připojení, přesunout **RGB** Terminálové služby **barva konstantní** uzlu **RGB** Terminálové služby **konečnou barvu** uzlu, a Přesuňte **Alpha** Terminálové služby **barva konstantní** uzlu **Alpha** Terminálové služby **konečnou barvu** uzlu. Tato připojení nastavit barvu konečné konstantu barva definované v předchozím kroku.

Následující obrázek znázorňuje dokončené shaderu graf a náhled shaderu použít na datovou krychli.

> [!NOTE]
> Na obrázku oranžovou barvu zadaná lépe předvedení účinek shaderu.

![Graf shaderu a jeho výsledek a 3&#45;D modelu](../designers/media/digit-flat-color-effect.png)

Určité tvarů může poskytovat lepší verze Preview pro některé shadery. Další informace o tom, jak zobrazit náhled shadery v Návrháři shaderu najdete v tématu [shaderu Návrhář](../designers/shader-designer.md).

## <a name="see-also"></a>Viz také:

- [Postupy: použití shaderu 3D modelu](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Postupy: Exportování shaderu](../designers/how-to-export-a-shader.md)
- [Návrhář shaderů](../designers/shader-designer.md)
- [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)
---
title: 'Postupy: Vytvoření shaderu základní barvy'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c301328a-079a-49e8-b688-4749c01657c0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f15bba37f5a03da934fae9ba4689da7775cfdb92
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62844862"
---
# <a name="how-to-create-a-basic-color-shader"></a>Postupy: Vytvoření shaderu základní barvy

Tento článek popisuje způsob použití návrháře shaderu a orientovaného grafu shaderu jazyka (DGSL) k vytvoření shaderu plochý barvy. Tento shader nastaví konečnou barvu na konstantní hodnotu barvy RGB.

## <a name="create-a-flat-color-shader"></a>Vytvoření shaderu plochý barvy

Můžete implementovat shaderu plochý barvy napsáním hodnota barvy RGB konstanty barvu na barvu závěrečný výstup.

Než začnete, ujistěte se, že **vlastnosti** okno a **nástrojů** jsou zobrazeny.

1. Vytvořte shader DGSL pracovat. Informace o tom, jak přidat do projektu DGSL shader naleznete v části Začínáme v [návrháře shaderu](../designers/shader-designer.md).

2. Odstranit **barva bodu** uzlu. Použití **vyberte** nástroj pro výběr **barva bodu** uzel a pak na panelu nabídek zvolte **upravit** > **odstranit**.

3. Přidat **barva konstantní** uzel do grafu. V **nástrojů**v části **konstanty**vyberte **barva konstantní** a přesuňte jej na návrhovou plochu.

4. Zadejte hodnotu barvy pro **barva konstantní** uzlu. Použití **vyberte** nástroj pro výběr **barva konstantní** uzel a pak na **vlastnosti** okno v **výstup** vlastnost, zadejte Hodnota barvy. Oranžová zadejte hodnotu (1.0, 0,5, 0.2, 1.0).

5. Připojte se k konečnou barvu barevnou konstantu. Chcete-li vytvořit připojení, přesuňte **RGB** z terminálu **barva konstantní** uzlu **RGB** z terminálu **konečnou barvu** uzel, a Přesuňte **alfa** z terminálu **barva konstantní** uzlu **alfa** z terminálu **konečnou barvu** uzlu. Tato připojení nastavte konečnou barvu na barvu konstanta definovaná v předchozím kroku.

Následující obrázek znázorňuje dokončené shader graf a náhled shaderu použitý pro datovou krychli.

> [!NOTE]
> Na obrázku byl zadán oranžovou barvou lépe demonstruje účinek shaderu.

![Graf shaderu a výsledek na 3&#45;D modelu](../designers/media/digit-flat-color-effect.png)

Určité tvary můžou poskytovat lepší verze Preview pro některé shadery. Další informace o tom, jak shadery v Návrháři shaderu ve verzi preview, najdete v části [návrháře shaderu](../designers/shader-designer.md).

## <a name="see-also"></a>Viz také:

- [Postupy: Použití shaderu na 3D model](../designers/how-to-apply-a-shader-to-a-3-d-model.md)
- [Postupy: Exportování shaderu](../designers/how-to-export-a-shader.md)
- [Návrhář shaderů](../designers/shader-designer.md)
- [Uzly návrháře shaderů](../designers/shader-designer-nodes.md)
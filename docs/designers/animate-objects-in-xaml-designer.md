---
title: Animace objektů v Návrháři XAML
ms.date: 04/11/2018
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 067ab2427bd0195a7919b6cd2bf909c2e60a5c54
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="animate-objects-in-xaml-designer"></a>Animace objektů v Návrháři XAML

Můžete vytvořit krátké animace, které přesun objektů nebo je objevovat a odhlášení.

Chcete-li začít, vytvořte *storyboard*. Scénář obsahuje jeden nebo více *časové osy*. Nastavit *klíčových snímků* na časové ose označit změny vlastností. Poté při spuštění animace Blend argument interpolaci změny vlastností po určenou dobu. Výsledkem je plynulý přechod. Můžete animace jakákoli vlastnost, která patří do objektu, a to ani v nevizuální vlastnosti.

Následující obrázek znázorňuje storyboard, s názvem **MoveUp**. Časová osa obsahuje klíčových snímků, které označit X a Y pomyslného obdélníku. Když je tato animace spuštěna, rámeček přesune z jednoho místa na jiný bez problémů.

![Scénáře MoveUp v Návrháři XAML](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png)

## <a name="see-also"></a>Viz také

- [Vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)
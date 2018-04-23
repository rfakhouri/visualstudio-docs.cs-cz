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
ms.openlocfilehash: 46b08815a320faf7043d860b4cd96f4120409854
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="animate-objects-in-xaml-designer"></a>Animace objektů v Návrháři XAML

Můžete vytvořit krátké animace, které přesun objektů nebo je objevovat a odhlášení.

Chcete-li začít, vytvořte *storyboard*. Scénář obsahuje jeden nebo více *časové osy*. Nastavit *klíčových snímků* na časové ose označit změny vlastností. Poté při spuštění animace Blend argument interpolaci změny vlastností po určenou dobu. Výsledkem je plynulý přechod. Můžete animace jakákoli vlastnost, která patří do objektu, a to ani v nevizuální vlastnosti.

Následující obrázek znázorňuje storyboard, s názvem **MoveUp**. Časová osa obsahuje klíčových snímků, které označit X a Y pomyslného obdélníku. Když je tato animace spuštěna, rámeček přesune z jednoho místa na jiný bez problémů.

![Scénáře MoveUp v Návrháři XAML](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png)

## <a name="see-also"></a>Viz také

- [Vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)
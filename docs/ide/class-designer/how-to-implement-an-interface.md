---
title: 'Postupy: Implementace rozhraní (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b1f427a78c11696253bdd418f5c8f7ac86b906bf
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "53916316"
---
# <a name="how-to-implement-an-interface-in-class-designer"></a>Postupy: Implementovat rozhraní v Návrháři tříd

V **návrhář tříd**, můžete implementovat rozhraní v diagramu tříd díky připojení k třídu, která poskytuje kód pro metody rozhraní. **Návrhář tříd** implementaci rozhraní vygeneruje a zobrazí vztah mezi rozhraní a třídy jako vztah dědičnosti. Kreslením čáru dědičnosti mezi rozhraní a třídy nebo přetažením rozhraní ze zobrazení tříd můžete implementovat rozhraní.

> [!TIP]
> Můžete vytvořit rozhraní stejným způsobem vytvoření jiných typů. Pokud rozhraní existuje, ale nezobrazí v diagramu tříd, pak nejprve zobrazí ji. Další informace najdete v tématu [jak: Vytváření typů pomocí návrháře tříd](how-to-create-types.md) a [jak: Zobrazení existujících typů](how-to-view-existing-types.md).

## <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>Pro implementaci rozhraní kreslením čáru dědičnosti

1.  V diagramu tříd zobrazte rozhraní a třídy, která implementuje rozhraní.

2.  Kreslení čáru dědičnosti z třídy a rozhraní.

     Lupy se zobrazí jako připojené ke třídě a popisek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje provizorní kód pro všechny členy rozhraní.

Další informace najdete v tématu [jak: Vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md).

## <a name="to-implement-an-interface-from-the-class-view-window"></a>Pro implementaci rozhraní z oken zobrazení tříd

1.  V diagramu tříd zobrazte třídu, která chcete implementovat rozhraní.

2.  Otevřít **zobrazení tříd** a vyhledejte rozhraní.

    > [!TIP]
    > Pokud **zobrazení tříd** není otevřený, otevřete **zobrazení tříd** z **zobrazení** nabídky nebo stisknutím klávesy **Ctrl**+**Shift** + **C**.

3.  Přetáhněte uzel rozhraní do třídy obrazec v diagramu.

     Lupy se zobrazí jako připojené ke třídě a popisek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje provizorní kód pro všechny členy rozhraní. v tomto okamžiku je implementovaná rozhraní.

## <a name="see-also"></a>Viz také:

- [Postupy: Vytváření typů pomocí návrháře tříd](how-to-create-types.md)
- [Postupy: Zobrazení existujících typů](how-to-view-existing-types.md)
- [Postupy: Vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md)
- [Refaktoring tříd a typů](refactoring-classes-and-types.md)
---
title: 'Postupy: Implementace rozhraní (návrhář tříd)'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e76aeea4c6779e97d882705e8680cd7a3b00d129
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62975174"
---
# <a name="how-to-implement-an-interface-in-class-designer"></a>Postupy: Implementovat rozhraní v Návrháři tříd

V **návrhář tříd**, můžete implementovat rozhraní v diagramu tříd díky připojení k třídu, která poskytuje kód pro metody rozhraní. **Návrhář tříd** implementaci rozhraní vygeneruje a zobrazí vztah mezi rozhraní a třídy jako vztah dědičnosti. Kreslením čáru dědičnosti mezi rozhraní a třídy nebo přetažením rozhraní ze zobrazení tříd můžete implementovat rozhraní.

> [!TIP]
> Můžete vytvořit rozhraní stejným způsobem vytvoření jiných typů. Pokud rozhraní existuje, ale nezobrazí v diagramu tříd, pak nejprve zobrazí ji. Další informace najdete v tématu [jak: Vytváření typů pomocí návrháře tříd](how-to-create-types.md) a [jak: Zobrazení existujících typů](how-to-view-existing-types.md).

## <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>Pro implementaci rozhraní kreslením čáru dědičnosti

1. V diagramu tříd zobrazte rozhraní a třídy, která implementuje rozhraní.

2. Kreslení čáru dědičnosti z třídy a rozhraní.

     Lupy se zobrazí jako připojené ke třídě a popisek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje provizorní kód pro všechny členy rozhraní.

Další informace najdete v tématu [jak: Vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md).

## <a name="to-implement-an-interface-from-the-class-view-window"></a>Pro implementaci rozhraní z oken zobrazení tříd

1. V diagramu tříd zobrazte třídu, která chcete implementovat rozhraní.

2. Otevřít **zobrazení tříd** a vyhledejte rozhraní.

    > [!TIP]
    > Pokud **zobrazení tříd** není otevřený, otevřete **zobrazení tříd** z **zobrazení** nabídky nebo stisknutím klávesy **Ctrl**+**Shift** + **C**.

3. Přetáhněte uzel rozhraní do třídy obrazec v diagramu.

     Lupy se zobrazí jako připojené ke třídě a popisek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje provizorní kód pro všechny členy rozhraní. v tomto okamžiku je implementovaná rozhraní.

## <a name="see-also"></a>Viz také:

- [Postupy: Vytváření typů pomocí Návrháře tříd](how-to-create-types.md)
- [Postupy: Zobrazení existujících typů](how-to-view-existing-types.md)
- [Postupy: Vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md)
- [Refaktoring tříd a typů](refactoring-classes-and-types.md)
---
title: Změna mezi zápisem člena & přidružení (návrhář tříd)
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- notation, member
- association notation
- member notation
- notation, association
ms.assetid: 65881c5a-d251-4a36-ad0d-73d088436092
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 17bda235f0fb5781b19a3b1384b86ae58543edf3
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/28/2019
ms.locfileid: "66261218"
---
# <a name="how-to-change-between-member-notation-and-association-notation-in-class-designer"></a>Postupy: Změna mezi zápisem člena a zápisem asociace v Návrháři tříd

V **návrhář tříd**, můžete změnit způsob, jakým diagram tříd reprezentuje vztah přidružení mezi dvěma typy z zápisem člena zápisem asociace a naopak. Členové zobrazí jako Asociační čáry často poskytují užitečné vizualizace z jak související typy.

> [!NOTE]
> Přidružení relace může být reprezentována jako člen vlastnost nebo pole. Chcete-li změnit zápisem člena pro zápisem asociace, musí mít jeden typ členem jiného typu. Chcete-li změnit zápisem asociace na zápisem člena, musí být připojen dva typy systémem Asociační čára. Další informace najdete v tématu [jak: Vytvoření přidružení typů bBetween](how-to-create-associations-between-types.md). Pokud váš projekt obsahuje více diagramů tříd, změny, které provedete tak, jak diagramu zobrazí vztahy přidružení ovlivňují pouze tento diagram. Chcete-li změnit způsob, jakým jiného diagramu zobrazí vztahy přidružení, otevřete nebo zobrazit tento diagram a proveďte tyto kroky.

## <a name="to-change-member-notation-to-association-notation"></a>Chcete-li změnit zápisem člena zápisem asociace

1. Z uzlu projektu v Průzkumníku řešení otevřete soubor diagramu tříd (.cd).

2. V obrazci typu v diagramu tříd, klikněte pravým tlačítkem na člen vlastnost nebo pole představující přidružení a zvolte **zobrazit jako přidružení**.

    > [!TIP]
    > Pokud jsou viditelné ve tvaru typu žádné vlastnosti nebo pole, jsou sbaleny oddílů ve tvaru. Pokud chcete rozšířit tvar typu, dvakrát klikněte na název oddílu nebo pravým tlačítkem myši na tvar typu a zvolte **Rozbalit**.

    Člen zmizí z prostoru ve tvaru typu a Asociační čára, zobrazí se dva typy připojení. Asociační čára označen názvem vlastnosti nebo pole.

## <a name="to-change-association-notation-to-member-notation"></a>Chcete-li změnit zápisem asociace zápisem člena

V diagramu tříd, pravým tlačítkem myši na Asociační čára a zvolte **zobrazit jako vlastnost** nebo **zobrazit jako pole** podle potřeby. Asociační čára zmizí, a vlastnost se zobrazí v odpovídající oddíl v rámci jeho tvar typu v diagramu.

## <a name="see-also"></a>Viz také:

- [Postupy: Vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md)
- [Postupy: Zobrazení dědičnosti mezi typy](how-to-view-inheritance-between-types.md)
- [Zobrazování typů a vztahů](designing-and-viewing-classes-and-types.md)
- [Postupy: Vizualizace asociace kolekce](how-to-visualize-a-collection-association.md)
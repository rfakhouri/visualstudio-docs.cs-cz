---
title: 'Postupy: Vizualizace asociace kolekce (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.collectionassociationline
- vs.classdesigner.ShowAssociationException
helpviewer_keywords:
- collection associations
- collections, collection associations
- Class Designer [Visual Studio], collection associations
ms.assetid: 54e39838-2fc9-4dc2-85b6-7e88a743108e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1b25a409b6e8476d1a1f18965b6796b2384ba98f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54961072"
---
# <a name="how-to-visualize-a-collection-association-in-class-designer"></a>Postupy: Vizualizace asociace kolekce v Návrháři tříd

Vlastnosti a pole, které jsou kolekce jiných typů lze zobrazit v diagramu tříd jako přidružení kolekce. Na rozdíl od pravidelných přidružení, které zobrazí pole nebo vlastnost jako řádku propojení vlastnící třídy typu pole, zobrazí se jako řádku propojení vlastnící třídy na shromážděný typ asociace kolekce.

## <a name="to-create-a-collection-association"></a>Vytvoření přidružení kolekce

1.  V kódu vytvořte vlastnost nebo pole, jehož typ je sám vytvořit kolekce silného typu.

2.  Rozbalte položku třídy tak, aby vlastnosti a pole se zobrazí v diagramu tříd.

3.  Ve třídě, klikněte pravým tlačítkem na pole nebo vlastnost a zvolte **zobrazit jako přidružení kolekce**.

Vlastnost nebo pole se zobrazí jako Asociační čára na shromážděný typ propojení.

## <a name="see-also"></a>Viz také:

- [Postupy: Vytvoření asociací mezi typy](how-to-create-associations-between-types.md)
- [Navrhování tříd a typů](designing-and-viewing-classes-and-types.md)

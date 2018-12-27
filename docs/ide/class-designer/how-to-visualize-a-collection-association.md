---
title: 'Postupy: Vizualizace asociace kolekce (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f2957492224f4d69a9536b4dfd6f47c136f72b0c
ms.sourcegitcommit: 935e341a02dba1c2aa3b6e89469388aa6e626f7f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53684061"
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

---
title: 'Postupy: Zobrazení dědičnosti mezi typy (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.AssociationTypeNotFoundError
helpviewer_keywords:
- types [Visual Studio], inheritance
- types [Visual Studio], base
- types [Visual Studio], derived
ms.assetid: ea3f0ada-f53b-4fb1-9fb5-908286f5ec3e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9c7a9700996244d653f7a5ce32b78f4edd145d3f
ms.sourcegitcommit: 935e341a02dba1c2aa3b6e89469388aa6e626f7f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53684480"
---
# <a name="how-to-view-inheritance-between-types-in-class-designer"></a>Postupy: Zobrazení dědičnosti mezi typy v Návrháři tříd

Pokud existuje mezi základního typu a jeho odvozeným typům v diagramu tříd v relaci dědičnosti najdete **návrhář tříd**. Chcete-li vytvořit vztah dědičnosti, pokud žádný neexistuje, mezi dvěma typy, přečtěte si téma [jak: Vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md).

## <a name="to-find-the-base-type"></a>Najít základní typ

1.  V diagramu tříd klikněte na typ, pro kterou chcete zobrazit základní třídu nebo rozhraní.

2.  Na **Diagram tříd** nabídce zvolte **zobrazit základní třídu** nebo **zobrazit základní rozhraní**.

     Základní třídu nebo rozhraní tohoto typu zobrazovat jako vybraný v diagramu. Všechny skryté Asociační čáry teď budou zobrazovat mezi dvěma tvary.

Můžete také kliknout pravým tlačítkem typ, jehož základní typ, který chcete zobrazit a zvolte **zobrazit základní třídu** nebo **zobrazit základní rozhraní**.

## <a name="to-find-the-derived-types"></a>Najít odvozené typy

1.  V diagramu tříd klikněte na typ, pro kterou chcete zobrazit odvozené třídy nebo rozhraní.

2.  Na **Diagram tříd** nabídce zvolte **Zobrazit odvozené třídy** nebo **Zobrazit odvozené rozhraní**.

     Typu odvozené třídy nebo rozhraní se zobrazí v diagramu. Všechny skryté Asociační čáry teď budou zobrazovat mezi tvary.

Můžete také kliknout pravým tlačítkem na typ, pro kterou chcete zobrazit jeho odvozených typů a zvolte **Zobrazit odvozené třídy** nebo **Zobrazit odvozené rozhraní**.

## <a name="see-also"></a>Viz také:

- [Postupy: Vytvoření asociací mezi typy](how-to-create-associations-between-types.md)
- [Zobrazování typů a vztahů](designing-and-viewing-classes-and-types.md)
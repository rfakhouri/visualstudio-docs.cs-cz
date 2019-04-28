---
title: 'Postupy: Vytvoření dědičnosti mezi typy (návrhář tříd)'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.inheritanceline
helpviewer_keywords:
- inheritance, relationship defining
- relationships, defining inheritance
ms.assetid: 3786a21c-8022-4bf5-9d13-740fd354e93c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5c1a4f8db08ec80714fe2cd74e4d1300d68a56e5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62975369"
---
# <a name="how-to-create-inheritance-between-types-in-class-designer"></a>Postupy: Vytvoření dědičnosti mezi typy v Návrháři tříd

Chcete-li vytvořit vztah dědičnosti mezi dvěma typy v diagramu třídy pomocí **návrhář tříd**, spojte se s jeho odvozený typ nebo typy základního typu. Můžete mít vztah dědičnosti mezi dvěma třídami, mezi třídou a rozhraní nebo mezi dvě rozhraní.

## <a name="to-create-an-inheritance-between-types"></a>Vytvoření dědičnosti mezi typy

1. Z projektu v **Průzkumníka řešení**, otevřete soubor diagramu tříd (.cd).

     Pokud nemáte k dispozici diagramu tříd, vytvořte ho. Zobrazit [jak: Přidání diagramů tříd do projektů](how-to-add-class-diagrams-to-projects.md).

2. V **nástrojů**v části **návrhář tříd**, klikněte na tlačítko **dědičnosti**.

3. V diagramu tříd kreslení čáru dědičnosti mezi typy, které potřebujete, od:

    - Odvozené třídy základní třídy

    - Implementující třída s implementovaným rozhraním

    - Rozšíření rozhraní pro rozšířené rozhraní

4. Nebo pokud máte odvozeným typem od obecného typu, klikněte na čáru dědičnosti. V **vlastnosti** okno, nastavte **argumenty typu** vlastnost tak, aby odpovídaly typ, který chcete použít pro obecného typu.

    > [!NOTE]
    > Nadřazené abstraktní třídy obsahuje alespoň jeden abstraktní člen, jsou všechny abstraktní členy implementovány jako neabstraktní dědičné třídy.
    >
    >  I když můžete vizualizovat existující obecné typy, nelze vytvořit nové obecné typy. Také nelze změnit parametry typu pro existující obecné typy.

## <a name="see-also"></a>Viz také:

- [Dědičnost](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)
- [Základní informace o dědičnosti](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)
- [Postupy: Zobrazení dědičnosti mezi typy](how-to-view-inheritance-between-types.md)
- [Třídy jazyka Visual C++ v Návrháři tříd](visual-cpp-classes.md)
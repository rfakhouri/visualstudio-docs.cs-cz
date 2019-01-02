---
title: 'Postupy: Vytvoření dědičnosti mezi typy (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.inheritanceline
helpviewer_keywords:
- inheritance, relationship defining
- relationships, defining inheritance
ms.assetid: 3786a21c-8022-4bf5-9d13-740fd354e93c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b94d89f6051b47f8500886348b335754abae9b72
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53925560"
---
# <a name="how-to-create-inheritance-between-types-in-class-designer"></a>Postupy: Vytvoření dědičnosti mezi typy v Návrháři tříd

Chcete-li vytvořit vztah dědičnosti mezi dvěma typy v diagramu třídy pomocí **návrhář tříd**, spojte se s jeho odvozený typ nebo typy základního typu. Můžete mít vztah dědičnosti mezi dvěma třídami, mezi třídou a rozhraní nebo mezi dvě rozhraní.

## <a name="to-create-an-inheritance-between-types"></a>Vytvoření dědičnosti mezi typy

1.  Z projektu v **Průzkumníka řešení**, otevřete soubor diagramu tříd (.cd).

     Pokud nemáte k dispozici diagramu tříd, vytvořte ho. Zobrazit [jak: Přidání diagramů tříd do projektů](how-to-add-class-diagrams-to-projects.md).

2.  V **nástrojů**v části **návrhář tříd**, klikněte na tlačítko **dědičnosti**.

3.  V diagramu tříd kreslení čáru dědičnosti mezi typy, které potřebujete, od:

    -   Odvozené třídy základní třídy

    -   Implementující třída s implementovaným rozhraním

    -   Rozšíření rozhraní pro rozšířené rozhraní

4.  Nebo pokud máte odvozeným typem od obecného typu, klikněte na čáru dědičnosti. V **vlastnosti** okno, nastavte **argumenty typu** vlastnost tak, aby odpovídaly typ, který chcete použít pro obecného typu.

    > [!NOTE]
    > Nadřazené abstraktní třídy obsahuje alespoň jeden abstraktní člen, jsou všechny abstraktní členy implementovány jako neabstraktní dědičné třídy.
    >
    >  I když můžete vizualizovat existující obecné typy, nelze vytvořit nové obecné typy. Také nelze změnit parametry typu pro existující obecné typy.

## <a name="see-also"></a>Viz také:

- [Dědičnost](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)
- [Základní informace o dědičnosti](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)
- [Postupy: Zobrazení dědičnosti mezi typy](how-to-view-inheritance-between-types.md)
- [Třídy jazyka Visual C++ v Návrháři tříd](visual-cpp-classes.md)
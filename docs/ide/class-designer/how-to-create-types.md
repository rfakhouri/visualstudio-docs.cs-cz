---
title: 'Postupy: Vytváření typů pomocí návrháře tříd'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.Clr.ClrAttributesDialog
helpviewer_keywords:
- custom attributes, applying
- class diagrams, creating types
- classes [Visual Studio], creating with Class Designer
- Class Designer [Visual Studio], creating classes
- types [Visual Studio], class diagrams
- attributes [Visual Studio], applying custom
ms.assetid: 94458c31-28bc-40e2-9737-85868788a0e5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d59c158bf8f532fa73a4eb2c22309218f80718e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-types-by-using-class-designer"></a>Postupy: vytváření typů pomocí návrháře tříd

Návrh nové typy pro C# a Visual Basic, projekty, vytvořte je v diagramu tříd. Existující typy najdete v sekci [postupy: zobrazení existujících typů](how-to-view-existing-types.md).

##  <a name="CreateType"></a> Vytvoření nového typu

1.  V **sada nástrojů**v části **návrhář tříd**, přetáhněte jednu z těchto na diagramu tříd:

    -   **Třída** nebo **abstraktní třídy**

    -   **výčet**

    -   **Rozhraní**

    -   **Struktura** (VB) nebo **struktura** (C#)

    -   **Delegát**

    -   **Modul** (pouze pro jazyka Visual Basic)

2.  Pojmenujte typ. Poté vyberte jeho úroveň přístupu.

3.  Vyberte soubor, do kterého chcete přidat počáteční kód pro daný typ:

    -   Chcete-li vytvořit nový soubor a přidat jej do aktuálního projektu, vyberte **vytvořit nový soubor** a název souboru.

    -   Chcete-li přidat kód do existující soubor, vyberte **přidat k existujícímu souboru**.

         Pokud má vaše řešení projekt, který sdílí kód mezi více aplikacemi, přidáte nový typ diagramu tříd v projektu aplikace, ale pouze pokud odpovídající soubor třída je ve stejné projektu aplikace nebo je ve sdílené projektu.

4.  Nyní přidejte další položky pro definování typu:

    |||
    |-|-|
    |**Pro**|**Přidat**|
    |Třídy, abstraktní třídy nebo struktury|Metody, vlastnosti, pole, události, konstruktory (metoda), destruktory (metoda) a konstanty, které určují typ|
    |Výčty|Hodnoty polí, které tvoří výčet|
    |Rozhraní|Metody, vlastnosti a události, které tvoří rozhraní|
    |Delegát|Parametry, které definují delegáta|
    |Modul|Metody, vlastnosti, pole, události, konstruktory (metoda) a konstanty, které určují modul|

     V tématu [vytváření členů](creating-and-configuring-type-members.md#create-members).

##  <a name="CustAttributeType"></a> Použít vlastní atribut typu

1.  Klikněte na tvar typu v diagramu tříd.

2.  V **vlastnosti**vedle možnosti **vlastní atributy** vlastnosti pro tento typ, klikněte na tlačítko se třemi tečkami (...).

3.  Přidejte jeden nebo více uživatelských atributů, vždy jeden na řádek. Nevkládejte je do závorek.

     Až skončíte, uživatelské atributy se použijí na typ.

##  <a name="CustAttributeMember"></a> Použít vlastní atribut u člena typu

1.  Klikněte na název člena ve tvaru jeho typu v diagramu tříd nebo na jeho řádku v okně Detaily třídy.

2.  V **vlastnosti**, najít člena **vlastní atributy** vlastnost.

3.  Přidejte jeden nebo více uživatelských atributů, vždy jeden na řádek. Nevkládejte je do závorek.

     Až skončíte, uživatelské atributy se použijí na typ.

## <a name="see-also"></a>Viz také

- [Postupy: vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md)
- [Postupy: vytvoření přidružení mezi typy](how-to-create-associations-between-types.md)
- [Vytváření a konfigurace členů typů](creating-and-configuring-type-members.md)
- [Práce s diagramy tříd](working-with-class-diagrams.md)
- [Navrhování tříd a typů](designing-and-viewing-classes-and-types.md)

---
title: "Postupy: vytváření typů pomocí návrháře tříd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.Clr.ClrAttributesDialog
helpviewer_keywords:
- custom attributes, applying
- class diagrams, creating types
- classes [Visual Studio], creating with Class Designer
- Class Designer [Visual Studio], creating classes
- types [Visual Studio], class diagrams
- attributes [Visual Studio], applying custom
ms.assetid: 94458c31-28bc-40e2-9737-85868788a0e5
caps.latest.revision: "41"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cf8691e4e38ae19aa1e8e04257f208241c02efac
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-types-by-using-class-designer"></a>Postupy: Vytváření typů pomocí návrháře tříd
Návrh nové typy pro projekty Visual Basic .NET a Visual C# .NET, vytvořte je v diagramu tříd. Existující typy najdete v sekci [postupy: zobrazení existujících typů (návrhář tříd)](../ide/how-to-view-existing-types-class-designer.md).  
  
-   [Vytvoření nového typu](#CreateType)  
  
-   [Použít vlastní atribut typu](#CustAttributeType)  
  
-   [Použít vlastní atribut u člena typu](#CustAttributeMember)  
  
##  <a name="CreateType"></a>Vytvoření nového typu  
  
1.  V sadě nástrojů v nabídce Návrhář tříd přetáhněte jeden z nich do diagramu tříd:  
  
    -   **Třída** nebo **abstraktní třídy**  
  
    -   **Výčet**  
  
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
  
     V tématu [vytváření členů](../ide/creating-and-configuring-type-members-class-designer.md#CreateMembers).  
  
##  <a name="CustAttributeType"></a>Použít vlastní atribut typu  
  
1.  Klikněte na tvar typu v diagramu tříd.  
  
2.  V okně Vlastnosti vedle **vlastní atributy** vlastnosti pro tento typ, klikněte na tlačítko se třemi tečkami (...).  
  
3.  Přidejte jeden nebo více uživatelských atributů, vždy jeden na řádek. Nevkládejte je do závorek.  
  
     Až skončíte, uživatelské atributy se použijí na typ.  
  
##  <a name="CustAttributeMember"></a>Použít vlastní atribut u člena typu  
  
1.  Klikněte na název člena ve tvaru jeho typu v diagramu tříd nebo na jeho řádku v okně Detaily třídy.  
  
2.  V okně vlastností najít člena **vlastní atributy** vlastnost.  
  
3.  Přidejte jeden nebo více uživatelských atributů, vždy jeden na řádek. Nevkládejte je do závorek.  
  
     Až skončíte, uživatelské atributy se použijí na typ.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření dědičnosti mezi typy (návrhář tříd)](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Postupy: vytvoření přidružení mezi typy (návrhář tříd)](../ide/how-to-create-associations-between-types-class-designer.md)   
 [Vytváření a konfigurace členů typů (návrhář tříd)](../ide/creating-and-configuring-type-members-class-designer.md)   
 [Práce s diagramy tříd (návrhář tříd)](../ide/working-with-class-diagrams-class-designer.md)   
 [Navrhování tříd a typů (návrhář tříd)](../ide/designing-classes-and-types-class-designer.md)
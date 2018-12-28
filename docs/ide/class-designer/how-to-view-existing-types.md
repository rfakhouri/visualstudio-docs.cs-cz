---
title: 'Postupy: Zobrazení existujících typů (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.CannotShowBaseType
helpviewer_keywords:
- types [Visual Studio], visualizing
- types [Visual Studio], class diagrams
- class diagrams, types
ms.assetid: de110a4e-5b51-4a40-9dee-615df4d8f999
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 16e1c31585296913647b5c3d641126c3abca22a8
ms.sourcegitcommit: 935e341a02dba1c2aa3b6e89469388aa6e626f7f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53684441"
---
# <a name="how-to-view-existing-types-in-class-designer"></a>Postupy: Zobrazení existujících typů v Návrháři tříd

Chcete-li zobrazit existující typ a její členy, přidáte jeho tvar do diagramu tříd.

Můžete vidět místní a odkazované typy. V aktuálně otevřeném projektu existuje místní typ a je pro čtení i zápis. Odkazovaný typ existuje v jiném projektu nebo v odkazovaném sestavení a je jen pro čtení.

Navrhování nových typů v diagramech tříd, naleznete v tématu [jak: Vytváření typů pomocí návrháře tříd](how-to-create-types.md).

## <a name="to-see-types-in-a-project-on-a-class-diagram"></a>Zobrazení typů v projektu v diagramu tříd

1.  Z projektu v **Průzkumníka řešení**, otevřete existující soubor diagramu tříd (.cd). Nebo pokud neexistuje žádný diagram tříd, přidejte do projektu nový diagram tříd. Zobrazit [jak: Přidání diagramů tříd do projektů](how-to-add-class-diagrams-to-projects.md).

2.  Z projektu v **Průzkumníka řešení**, přetáhněte soubor zdrojového kódu do diagramu tříd.

    > [!NOTE]
    > Pokud má vaše řešení projekt, které sdílejí kód mezi více aplikacemi, můžete přetáhnout soubory nebo kód do diagramu tříd pouze z těchto zdrojů:
    >
    > - Projekt aplikace, který obsahuje diagram
    > - Sdílený projekt, který byl importován projektem aplikace
    > - Odkazovaný projekt
    > - Sestavení

    Tvary, které představují typy definované v souboru zdrojového kódu, se zobrazí v diagramu na pozici, kam jste soubor přetáhli.

Můžete také zobrazit typy v projektu přetažením jednoho nebo více typů z uzlu projektu v **zobrazení tříd** do diagramu tříd.

> [!TIP]
> Pokud **zobrazení tříd** není otevřený, otevřete **zobrazení tříd** z **zobrazení** nabídky.

Chcete-li zobrazit typy ve výchozích umístěních v diagramu, vyberte jeden nebo více typů v **zobrazení tříd**, klikněte pravým tlačítkem na vybrané typy a zvolte **zobrazit Diagram tříd**.

> [!NOTE]
> Pokud v projektu existuje zavřený diagram tříd obsahující daný typ, diagram tříd se otevře a zobrazí tvar typu. Nicméně pokud žádné diagram tříd obsahující typ v projektu existuje, **návrhář tříd** vytvoří v projektu nový diagram tříd a otevře jej pro zobrazení typu.

Při prvním zobrazení typu v diagramu se jeho tvar ve výchozím nastavení zobrazí sbalený. Tvar můžete rozbalit a zobrazit jeho obsah.

### <a name="to-display-the-contents-of-a-project-in-a-class-diagram"></a>Chcete-li zobrazit obsah projektu v diagramu tříd

V **Průzkumníka řešení** nebo **zobrazení tříd**, klikněte pravým tlačítkem na projekt a zvolte **zobrazení**, klikněte na tlačítko **zobrazit Diagram tříd**. Vytvoří se automaticky vyplněný diagram tříd.

## <a name="see-also"></a>Viz také:

- [Postupy: Zobrazení dědičnosti mezi typy](how-to-view-inheritance-between-types.md)
- [Postupy: Přizpůsobení diagramů tříd](how-to-customize-class-diagrams.md)
- [Zobrazování typů a vztahů](designing-and-viewing-classes-and-types.md)
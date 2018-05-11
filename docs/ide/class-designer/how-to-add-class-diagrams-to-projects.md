---
title: 'Postupy: Přidání diagramů tříd do projektů (návrhář tříd)'
ms.date: 05/08/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- class diagrams, creating
- Class Designer [Visual Studio], opening
ms.assetid: 0eac1b54-2711-4e4b-9654-a0c429c08c8f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 94e13d4c1dbda200c2e2660e4b3b44e62ed99496
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="how-to-add-class-diagrams-to-projects"></a>Postupy: Přidání diagramů tříd do projektů

K návrhu, upravit a Refaktorovat třídami a ostatními typy, přidejte do projektu C#, Visual Basic nebo C++ diagramu tříd. K vizualizaci různé části kódu v projektu, přidejte více diagramů tříd do projektu.

Diagramy tříd nelze vytvořit z projektů, které sdílejí kód mezi více aplikacemi. Vytváření diagramů tříd UML naleznete v tématu [vytvořit modelování projektů a diagramů UML](../../modeling/create-uml-modeling-projects-and-diagrams.md).

## <a name="install-the-class-designer-component"></a>Nainstalovat součást návrhář tříd

Pokud používáte Visual Studio 2017 a nebyly nainstalovány **návrhář tříd** součást, postupujte podle těchto kroků nainstalujte ho.

1. Otevřete **instalační program Visual Studio** z nabídky Start nebo výběrem **nástroje** > **funkcí a nástrojů pro získání** z řádku nabídek v sadě Visual Studio.

   **Instalační program Visual Studio** otevře.

1. Vyberte **jednotlivých součástí** kartě a poté přejděte dolů k **Code nástroje** kategorie.

1. Vyberte **návrhář tříd** a pak vyberte **upravit**.

   ![Třídy součástí návrháře instalační program Visual Studio](media/class-designer-component.png)

   **Návrhář tříd** součást zahájena instalace.

## <a name="add-a-blank-class-diagram-to-a-project"></a>Přidání do projektu diagram prázdné – třída

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a potom zvolte **přidat** > **novou položku**. Také můžete stisknout klávesu **Ctrl**+**Shift**+**A**.

   **Přidat novou položku** otevře se dialogové okno.

2. Rozbalte položku **společné položky** > **Obecné**a potom vyberte **diagramu tříd** ze seznamu šablony. Projekty Visual C++, najdete **nástroj** Chcete-li najít **diagramu tříd** šablony.

   > [!NOTE]
   > Pokud nevidíte **diagramu tříd** šablony, [postupujte podle kroků](#install-the-class-designer-component) k instalaci **návrhář tříd** součásti pro sadu Visual Studio.

   Diagram třídy otevře v Návrháři tříd a zobrazí se jako soubor, který má *.cd* rozšíření v **Průzkumníku řešení**. Můžete přetáhnout tvary a čáry diagramu z **sada nástrojů**.

Chcete-li přidat více diagramů tříd, opakujte kroky v tomto postupu.

## <a name="add-a-class-diagram-based-on-existing-types"></a>Přidat na základě existující typů diagram – třída

V **Průzkumníku řešení**, otevřete místní nabídky souboru třídy a pak zvolte **zobrazení diagramu tříd**.

-nebo-

V **zobrazení tříd**, otevřete v místní nabídce obor názvů nebo typ a potom zvolte **zobrazení diagramu tříd**.

## <a name="to-display-the-contents-of-a-complete-project-in-a-class-diagram"></a>Chcete-li zobrazit obsah dokončený projekt v diagramu tříd

V **Průzkumníku řešení** nebo třída zobrazení, klikněte pravým tlačítkem na projekt a zvolte **zobrazení**, zvolte **zobrazení diagramu tříd**.

Diagramu automaticky vyplněna třída se vytvoří.

## <a name="see-also"></a>Viz také

- [Postupy: vytváření typů pomocí návrháře tříd](how-to-create-types.md)
- [Postupy: zobrazení existujících typů](how-to-view-existing-types.md)
- [Návrh a zobrazení tříd a typů](designing-and-viewing-classes-and-types.md)
- [Zobrazení typů a vztahů](viewing-types-and-relationships.md)
- [Práce s diagramy tříd](working-with-class-diagrams.md)

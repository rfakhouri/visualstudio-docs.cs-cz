---
title: Práce s diagramem definice DSL
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.diagram
- vs.dsltools.dsldesigner.dsldiagram
helpviewer_keywords:
- Domain-Specific Language Tools, diagram
- Domain-Specific Language Tools, Split Tree
- Domain-Specific Language Tools, Show Map Lines
- Domain-Specific Language Tools, Show As Class
- Domain-Specific Language Tools, Bring Tree Here
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 45436775c2e7cd2d8ba057b9bdb2e3a3f80d7493
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="working-with-the-dsl-definition-diagram"></a>Práce s diagramem definice DSL
Diagram nástroje [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] definice je důležitým nástrojem pro definování jazyka domény. Můžete přidat elementy k vaší doméně modelu a definovat vztahy v diagramu, a můžete upravit rozložení diagramu, aby byl čitelnější.

## <a name="the-layout-of-the-diagram"></a>Rozložení diagramu
 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] Definice diagramu má dva oddíly **třídy a vztahy** oddílu a **elementy diagramu** oddílu. **Třídy a vztahy** oddílu zobrazí třídy domény a vztahy domén a dědičnosti. **Elementy diagramu** oddílu zobrazí tvar třídy, konektor třídy, třídy dráha a vygenerovaný návrháře diagram.

 Třídy domény může vyskytovat na několika místech aplikace **třídy a vztahy** oddíly. Definice třídy domény zobrazí ve stromu dědičnosti, pokud je základní třídou pro jiné třídy domény a vztahy stromu, pokud je zdroj vztahy vložení nebo odkaz. Třída zástupné domény se zobrazují jako cíle vztahy vložení nebo odkaz. Ve výchozím nastavení jsou elementy zástupný symbol zobrazí s **vlastnosti domény** prostředí sbalené. Dědičnost nebo vložení nebo odkaz relace se nezobrazují.

 Když přidáte třídy domény, zobrazí se v dolní části **třídy a vztahy** oddílu. Když přidáte vložení nebo referenční relace, vykreslením pod a napravo od domény třída zdroje.

 Při přidávání třídy domény a vztahy, může přestat obtížné vyhledat konkrétní domény třídu. Můžete najít třídu domény kliknutím pravým tlačítkem myši v **DSL Explorer** a pak levým na **vyhledejte v diagramu**.

 Následující části popisují, jak můžete změnit vzhled diagramu, aby bylo snazší ke čtení.

## <a name="copying-elements"></a>Kopírování prvků
 Můžete použít kopírování, vyjmout a vložit na elementy v diagramu DSL definice.

## <a name="zooming-in-or-out-on-the-diagram"></a>Zvětšování nebo zmenšování diagram.
 Můžete zvětšit nebo zmenšit v diagramu pomocí **DSL Návrhář** nástrojů nastavení úrovně přiblížení.

## <a name="hiding-map-lines"></a>Skrytí mapy řádky
 Mapa řádky jsou řádky, které jsou vykreslovány mezi domény třídu nebo vztah domény a tvar nebo konektor, který je namapovaný. Můžete skrýt čar mapy, kliknutím **zobrazit čáry mapy** na tlačítko **DSL Návrhář** panelu nástrojů. Chcete-li zobrazit čáry, klikněte na tlačítko znovu.

## <a name="changing-the-diagram-layout"></a>Změna rozložení diagramu
 Můžete změnit rozložení **třídy a vztahy** oddílu následujícím způsobem.

### <a name="expandcollapse"></a>Rozbalit nebo sbalit
 Můžete snížit velikost elementu obrazce prostředí, který představuje třídu domény nebo obrazce pravým tlačítkem myši a potom kliknutím na **sbalit**. Skryje **vlastnosti domény** prostředí tvaru. Chcete-li zobrazit **vlastnosti domény** prostoru pro znovu, pravým tlačítkem myši a pak klikněte na tlačítko **rozbalte**.

### <a name="move-updown"></a>Přesunout nahoru/dolů
 Pravým tlačítkem myši na prvek a potom klikněte na můžete přesunutí domény třídu nebo diagram elementu nahoru nebo dolů v oddílu **nahoru** nebo **přesunout dolů**. Pokud přesunete element zástupný symbol, který se zobrazí jako cíl pro relaci vložení nebo odkaz, relace se přesune s ním.

### <a name="expandcollapse-relationships-tree"></a>Rozbalit nebo sbalit stromu vztahů
 Pokud třída domény hrají roli zdroj při vložení nebo odkaz relace se ostatní třídy domény, můžete skrýt vztahy pravým tlačítkem myši na definici třídy domény a pak kliknutím na **stromu vztahů sbalit**. Zobrazit vztahy, klikněte pravým tlačítkem na element definice a potom klikněte na **rozbalte strom vztahy**.

### <a name="expandcollapse-inheritance-tree"></a>Rozbalit nebo sbalit stromu dědičnosti
 Pokud třída domény je základní třídou třídy jiné domény, můžete skrýt stromu dědičnosti, pravým tlačítkem myši na definici třídy domény a pak kliknutím na **stromu dědičnosti sbalit**. Chcete-li zobrazit stromu dědičnosti, klikněte pravým tlačítkem na element definice a potom klikněte na **rozbalte strom dědičnosti**.

### <a name="bring-tree-here"></a>vložení stromu zde
 Diagram může konsolidovat kliknete pravým tlačítkem na třídu zástupný symbol domény a pak kliknutím na **přineste zde stromu**. Třída domény zástupný text se změní na element definice a zobrazí dědičnosti a vztahy stromy. Element bývalé definice stane prvku zástupného symbolu, pokud je cílem relace nebo podřízený objekt v relaci dědičnosti; v opačném zmizí.

### <a name="split-tree"></a>rozdělit strom
 Můžete rozdělit dědičnosti nebo vztahy stromy pravým tlačítkem myši na definici třídy domény, který zobrazuje je a pak kliknutím na **rozdělení stromu**. Element definice stane zástupný text elementu a definice třídy domény, společně s jeho dědičnosti a vztahy stromy, se nyní zobrazí v dolní části oddílu.

### <a name="show-as-class"></a>zobrazit jako třídu
 Pokud relace domény má odvozený relace, nebo pokud má vložení nebo odkaz relace se vztahy jiných domén, můžete zobrazit relace jako třída pravým tlačítkem myši na relaci a potom kliknutím na **zobrazit jako – třída** . Relace se zobrazí **vlastnosti domény** prostoru pro a zobrazí stromy dědičnosti a vztahy.

## <a name="see-also"></a>Viz také

- [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
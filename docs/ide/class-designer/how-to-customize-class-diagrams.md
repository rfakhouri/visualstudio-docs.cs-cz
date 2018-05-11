---
title: 'Postupy: Přizpůsobení diagramů tříd (návrhář tříd)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- class diagrams, customizing
- shapes, removing type from class diagrams
- type shapes, removing from class diagrams
- class diagrams, removing type shapes
ms.assetid: e9030aea-c77d-4cc1-b8f6-b6ca469b692d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8ed2a6112d59e5d433201a417d8d85fd6683b36d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="how-to-customize-class-diagrams"></a>Postupy: přizpůsobení diagramů tříd

Můžete změnit způsob, jak diagramy tříd zobrazují informace. Můžete přizpůsobit celý diagram nebo jednotlivé typy na ploše návrhu.

Můžete například upravit úroveň zvětšení celého diagramu tříd, změnit způsob seskupování a řazení jednotlivých členů typu, skrýt nebo zobrazit vztahy a přesunout jednotlivé typy nebo množiny typů kamkoli v diagramu.

> [!NOTE]
> Upravením způsobu, jakým se tvary v diagramu zobrazují, nezměníte základní kód pro typy znázorněné v diagramu.

Oddíly, které obsahují zadejte členy, například **vlastnosti** část v třídě, se nazývají přihrádky. Jednotlivé oddíly a členy typu můžete skrýt nebo zobrazit.

## <a name="zoom-in-and-out-of-the-class-diagram"></a>Přiblížení a oddálení diagramu tříd

1. Otevřete a vyberte soubor diagramu tříd v **návrhář tříd**.

2. Na **návrhář tříd** nástrojů, klikněte na tlačítko **přiblížit** nebo **Oddálit** tlačítko změnit úroveň přiblížení plochu návrháře.

     or

     Zadejte hodnotu přiblížení. Můžete použít **zvětšení** rozevíracím seznamu nebo zadejte platný přiblížení úroveň (platný rozsah je od 10 % až 400 %).

    > [!NOTE]
    > Změna úrovně přiblížení neovlivní měřítko výtisku vašeho diagramu tříd.

## <a name="customize-grouping-and-sorting-of-type-members"></a>Přizpůsobení seskupování a řazení členů typu

1. Otevřete a vyberte soubor diagramu tříd v **návrhář tříd**.

2. Klikněte pravým tlačítkem myši na prázdnou oblast na návrhovou plochu a přejděte na **členy skupiny**.

3. Vyberte jednu z dostupných možností:

    - **Seskupit podle druhu** odděluje jednotlivé typ členy do seskupené seznam vlastností, metody, události a pole. Jednotlivé skupiny závisí na definici entit: třída například nebude zobrazovat žádnou skupinu událostí, pokud pro danou třídu zatím nebyly definovány žádné události.

    - **Seskupit podle přístup** odděluje jednotlivé typ členů do seznamu seskupené podle člena přístup modifikátory. Například veřejné a soukromé.

    - **Seřadit podle abecedy** zobrazí položky, které tvoří entitu jako jeden abecední seznam. Seznam je seřazen vzestupně.

## <a name="hide-compartments-on-a-type"></a>Skrytí oddílů typu

1. Otevřete a vyberte soubor diagramu tříd v **návrhář tříd**.

2. Klikněte pravým tlačítkem na kategorii členů v typu, který chcete přizpůsobit (například vyberte **metody** uzlu v třídě.

3. Klikněte na tlačítko **skrýt prostředí**.

     Vybraný oddíl zmizí z kontejneru typu.

## <a name="hide-individual-members-on-a-type"></a>Skrytí jednotlivých členů typu

1. Otevřete a vyberte soubor diagramu tříd v **návrhář tříd**.

2. Klikněte pravým tlačítkem myši na člen v typu, který chcete skrýt.

3. Klikněte na tlačítko **skrýt**.

     Vybraný člen zmizí z kontejneru typu.

## <a name="show-hidden-compartments-and-members-on-a-type"></a>Zobrazení skrytých oddílů a členů typu

1. Otevřete a vyberte soubor diagramu tříd v **návrhář tříd**.

2. Klikněte pravým tlačítkem na název typu se skrytým oddílem.

3. Klikněte na tlačítko **zobrazit všechny členy**.

     Všechny skryté oddíly a členy se zobrazí v kontejneru typu.

## <a name="hide-relationships"></a>Skrytí vztahů

1. Otevřete a vyberte soubor diagramu tříd v **návrhář tříd**.

2. Klikněte pravým tlačítkem myši na asociační čáru nebo čáru dědičnosti, kterou chcete skrýt.

3. Klikněte na tlačítko **skrýt** pro Asociační čáry a klikněte na **skrýt řádek dědičnosti** pro dědičnosti řádky.

4. Klikněte na tlačítko **zobrazit všechny členy**.

     Všechny skryté oddíly a členy se zobrazí v kontejneru typu.

## <a name="show-hidden-relationships"></a>Zobrazení skrytých vztahů

1. Otevřete a vyberte soubor diagramu tříd v **návrhář tříd**.

2. Klikněte pravým tlačítkem na typ se skrytým přidružením nebo dědičností.

 Klikněte na tlačítko **zobrazit všechny členy** pro Asociační čáry a klikněte na **zobrazit základní třída** nebo **Zobrazit odvozené třídy** pro dědičnosti řádky.

## <a name="remove-a-shape-from-a-class-diagram"></a>Odebrání tvaru z diagramu tříd
Můžete odebrat tvar typu z diagramu tříd bez ovlivnění základního kódu typu. Odebrání tvarů typu z diagramu tříd ovlivní pouze tento diagram: základní kód definující typ a ostatní diagramy, které typ zobrazují, ovlivněny nejsou.

1. V diagramu tříd vyberte tvar typu, který chcete z diagramu odebrat.

2. Na **upravit** nabídce zvolte **odebrání Diagram**.

     Tvar typu a čáry přidružení nebo dědičnosti spojené s tvarem se již v diagramu nezobrazí.

## <a name="delete-a-type-shape-and-its-underlying-code"></a>Odstranění tvaru typu a jeho základního kódu

1. Klikněte pravým tlačítkem myši na tvar na návrhové ploše.

2. Vyberte **odstranit kód** v místní nabídce.

     Tvar je odstraněn z diagramu a jeho základní kód je odstraněn z projektu.

## <a name="see-also"></a>Viz také

- [Práce s diagramy tříd](working-with-class-diagrams.md)
- [Postupy: změna mezi zápisem člena a zápisem asociace](how-to-change-between-member-notation-and-association-notation.md)
- [Postupy: zobrazení existujících typů](how-to-view-existing-types.md)
- [Zobrazování typů a vztahů](viewing-types-and-relationships.md)
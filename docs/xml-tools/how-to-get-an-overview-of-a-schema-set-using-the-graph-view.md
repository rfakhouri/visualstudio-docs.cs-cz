---
title: 'Postupy: získání přehledu sady schématu pomocí zobrazení grafu ve schématu XML návrháře'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4feb40ba843da5c3f2e5f7de9b8d554debf6fcc6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Postupy: získání přehledu sady schématu pomocí zobrazení grafu

Toto téma popisuje postup použití [zobrazení grafu](../xml-tools/graph-view.md) zobrazíte souhrnné zobrazení uzlů ve schématu sady a vztahy mezi uzly.

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Vytvořte nový soubor XSD a zobrazte kořenový element v modelu zobrazení obsahu

1.  Vytvoření nového souboru schématu XML a uložte soubor jako Relationships.xsd.

2.  Klikněte **pomocí editoru XML k zobrazení a úpravě podkladový soubor schématu XML** odkaz na zobrazení spustit.

3.  Zkopírujte schématu XML ukázkový kód z [schématu XML ukázka: vztahy](../xml-tools/sample-xsd-file-relationships.md) a vložte jej nahradit kód, který byl přidán nový soubor XSD ve výchozím nastavení.

4.  Klikněte pravým tlačítkem na libovolné místo v editoru XML a vyberte **Návrhář zobrazení**.

5.  Na panelu nástrojů XSD vyberte zobrazení grafu.

6.  Vyberte **schématu nastavit** uzlu v Průzkumníku schématu XML a přetáhněte uzel návrhu suface zobrazení grafu. Měli byste vidět všechny uzly globální a šipky připojení uzly, které mají relace.

     ![Graf zobrazení](../xml-tools/media/relationshipingraphview.gif "RelationshipInGraphView")

7.  Klikněte na libovolný uzel na návrhovou plochu a podívejte se na navigačního panelu zobrazit umístění vybraného uzlu v sadě schématu.

8.  Rick, klikněte na libovolný uzel elementu na desing plochy a vyberte možnost **Generovat XML ukázka** zobrazíte instance dokumentu XML.
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
ms.openlocfilehash: 05f690d76d61ffd52abbc7b73cf162d7f6609708
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751894"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Postupy: získat přehled o schéma nastavit pomocí zobrazení grafu

Toto téma popisuje postup použití [zobrazení grafu](../xml-tools/graph-view.md) zobrazíte souhrnné zobrazení uzlů ve schématu sady a vztahy mezi uzly.

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Vytvořte nový soubor XSD a zobrazte kořenový element v modelu zobrazení obsahu

1.  Vytvoření nového souboru schématu XML a soubor uložte jako *Relationships.xsd*.

2.  Klikněte **pomocí editoru XML k zobrazení a úpravě podkladový soubor schématu XML** odkaz na zobrazení spustit.

3.  Zkopírujte schématu XML ukázkový kód z [schématu ukázka XML: vztahy](../xml-tools/sample-xsd-file-relationships.md) a vložte jej nahradit kód, který byl přidán nový soubor XSD ve výchozím nastavení.

4.  Klikněte pravým tlačítkem na libovolné místo v editoru XML a vyberte **Návrhář zobrazení**.

5.  Vyberte zobrazení grafu z **XSD nástrojů**.

6.  Vyberte **schématu nastavit** uzel v **Explorer schématu XML** a přetáhněte uzel k návrhu suface zobrazení grafu. Měli byste vidět všechny uzly globální a šipky připojení uzly, které mají relace.

     ![Zobrazení grafu](../xml-tools/media/relationshipingraphview.gif)

7.  Klikněte na libovolný uzel na návrhovou plochu a podívejte se na navigačního panelu zobrazit umístění vybraného uzlu v sadě schématu.

8.  Rick, klikněte na libovolný uzel elementu na desing plochy a vyberte možnost **Generovat XML ukázka** zobrazíte instance dokumentu XML.
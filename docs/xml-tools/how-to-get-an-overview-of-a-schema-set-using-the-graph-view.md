---
title: 'Postupy: získání přehledu sady schématu pomocí zobrazení grafu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 145a55312d042811b0d51d46136078657d10fee1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Postupy: získání přehledu sady schématu pomocí zobrazení grafu
Toto téma popisuje postup použití [zobrazení grafu](../xml-tools/graph-view.md) zobrazíte souhrnné zobrazení uzlů ve schématu sady a vztahy mezi uzly.  
  
### <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Vytvořte nový soubor XSD a zobrazte kořenový element v modelu zobrazení obsahu  
  
1.  Vytvoření nového souboru schématu XML a uložte soubor jako Relationships.xsd.  
  
2.  Klikněte **pomocí editoru XML k zobrazení a úpravě podkladový soubor schématu XML** odkaz na zobrazení spustit.  
  
3.  Zkopírujte schématu XML ukázkový kód z [schématu XML ukázka: vztahy](../xml-tools/sample-xsd-file-relationships.md) a vložte jej nahradit kód, který byl přidán nový soubor XSD ve výchozím nastavení.  
  
4.  Klikněte pravým tlačítkem na libovolné místo v editoru XML a vyberte **Návrhář zobrazení**.  
  
5.  Na panelu nástrojů XSD vyberte zobrazení grafu.  
  
6.  Vyberte **schématu nastavit** uzlu v Průzkumníku schématu XML a přetáhněte uzel návrhu suface zobrazení grafu. Měli byste vidět všechny uzly globální a šipky připojení uzly, které mají relace.  
  
     ![Graf zobrazení](../xml-tools/media/relationshipingraphview.gif "RelationshipInGraphView")  
  
7.  Klikněte na libovolný uzel na návrhovou plochu a podívejte se na navigačního panelu zobrazit umístění vybraného uzlu v sadě schématu.  
  
8.  Rick, klikněte na libovolný uzel elementu na desing plochy a vyberte možnost **Generovat XML ukázka** zobrazíte instance dokumentu XML.
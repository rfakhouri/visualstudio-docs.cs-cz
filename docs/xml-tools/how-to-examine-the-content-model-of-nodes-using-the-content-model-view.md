---
title: Zkontrolujte modelu obsahu uzlů v zobrazení obsahu modelu Návrhář schématu XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: c42ddac8-b0e3-48d6-9832-112a19d6c104
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2bb1bcc13ad908b69a847662178cd6cd13aeec6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-examine-the-content-model-of-nodes-using-the-content-model-view"></a>Postupy: Zkontrolujte modelu obsahu uzlů pomocí zobrazení modelu obsahu

Toto téma popisuje, jak prozkoumat pomocí uzlů [zobrazení obsahu modelu](../xml-tools/content-model-view.md).

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Vytvořte nový soubor XSD a zobrazte kořenový element v modelu zobrazení obsahu

1.  Vytvořte nový soubor schématu XML.

2.  Klikněte na tlačítko **pomocí editoru XML k zobrazení a úpravě podkladový soubor schématu XML** zobrazení spustit.

3.  Zkopírujte schématu XML ukázkový kód z [schématu XML ukázka: schéma pořadí nákupu](../xml-tools/sample-xsd-file-purchase-order-schema.md) a vložte jej nahradit kód, který byl přidán nový soubor XSD ve výchozím nastavení.

4.  Vyberte `purchaseOrder` element v Průzkumníku schématu kliknutím pravým tlačítkem myši `purchaseOrder` element v editoru XML a výběrem **zobrazit v Průzkumníku XML**.

5.  Klikněte pravým tlačítkem myši `purchaseOrder` v Průzkumníku XML a vyberte **zobrazit v zobrazení obsahu modelu**.

     Zobrazí zobrazení obsahu modelu `purchaseOrder` elementu na jeho návrhovou plochu.

6.  Rozbalte `shipTo`, `billTo`, a `items` uzlů poklepáním na každém uzlu nebo kliknutím na dvojitou šipku napravo od každého uzlu.

     Uzly `purchaseOrder` element jsou nyní rozšířit a zobrazí se model obsahu elementu.

7.  Klikněte na libovolný uzel v rámci `purchaseOrder` elementu a podívejte se na navigačního panelu zobrazit, kde v sadě schématu vybraný uzel nachází.

8.  Klikněte **zobrazit dokumentaci** tlačítka na panelu nástrojů XSD k přepnutí jejich. Klikněte pravým tlačítkem na návrhovou plochu k přepnutí v dokumentaci.

9. Rick kliknutím `purchaseOrder` uzel a vyberte možnost **Generovat XML ukázka** zobrazíte instance dokumentu XML.
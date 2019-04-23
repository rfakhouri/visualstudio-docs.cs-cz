---
title: Prozkoumání modelu obsahu uzlů pomocí zobrazení modelu obsahu v Návrháři schémat XML
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c42ddac8-b0e3-48d6-9832-112a19d6c104
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dfefc7d6aaa40d628cc0ee9d582fddf65adb411e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60052607"
---
# <a name="how-to-examine-the-content-model-of-nodes-using-the-content-model-view"></a>Postupy: Prozkoumání modelu obsahu uzlů pomocí zobrazení modelu obsahu

Toto téma popisuje, jak prozkoumat uzly pomocí [zobrazení modelu obsahu](../xml-tools/content-model-view.md).

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Vytvořte nový soubor XSD a zobrazte kořenový element v zobrazení modelu obsahu

1. Vytvořte nový soubor schématu XML.

2. Klikněte na tlačítko **editoru XML použijte k zobrazení a úpravě základního souboru schématu XML** na zobrazení spuštění.

3. Zkopírujte ukázkový kód XML schéma z [ukázky XML schématu: nákupní pořadí schématu](../xml-tools/sample-xsd-file-purchase-order-schema.md) a vložte ji nahradit kód, který byl přidán do nového souboru XSD ve výchozím nastavení.

4. Vyberte `purchaseOrder` element ve schématu Explorer kliknutím pravým tlačítkem myši `purchaseOrder` element v XML editor a vyberete **zobrazit v Průzkumníkovi XML**.

5. Klikněte pravým tlačítkem myši `purchaseOrder` v Průzkumníku XML a vyberte **zobrazit v zobrazení modelu obsahu**.

     Zobrazení modelu obsahu se zobrazí `purchaseOrder` prvek na jeho návrhovou plochu.

6. Rozbalte `shipTo`, `billTo`, a `items` uzlů poklepáním na každém uzlu nebo kliknutím na dvojitou šipku vpravo od každého uzlu.

     Uzly `purchaseOrder` prvek nyní rozbaleny a zobrazí se model obsahu prvku.

7. Klikněte na libovolný uzel v rámci `purchaseOrder` elementu a podívejte se na panelu s popisem cesty chcete zobrazit, kde v sadě schémat vybraný uzel se nachází.

8. Klikněte na tlačítko **zobrazit dokumentaci** tlačítko na panelu nástrojů XSD, chcete-li přepnout jejich. Klikněte pravým tlačítkem na návrhové ploše, chcete-li přepnout v dokumentaci.

9. Rick kliknutím `purchaseOrder` uzel a vyberte možnost **generovat ukázkové XML** zobrazíte instance dokumentu XML.
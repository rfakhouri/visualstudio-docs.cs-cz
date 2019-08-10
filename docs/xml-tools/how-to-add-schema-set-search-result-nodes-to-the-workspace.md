---
title: Přidat uzly výsledků hledání sady schémat XML do pracovního prostoru
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c2718c08b36ff9ef3ca8ae06f7d511cacb8fa73c
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923660"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>Postupy: Přidání uzlů výsledků hledání v sadě schémat do pracovního prostoru

Toto téma vysvětluje, jak přidat uzly, které jsou zvýrazněny v **Průzkumníku schémat XML** jako výsledek hledání klíčového slova v pracovním prostoru.

> [!NOTE]
> Do [pracovního prostoru](../xml-tools/xml-schema-designer-workspace.md)lze přidat pouze globální uzly.

V tomto příkladu se používá ukázka [schématu nákupní objednávky](../xml-tools/sample-xsd-file-purchase-order-schema.md).

## <a name="to-add-schema-set-result-nodes"></a>Postup přidání uzlů výsledků sady schémat

1. Postupujte podle kroků v [tématu Postupy: Vytvořte a upravte soubor](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)schématu XSD.

2. Do textového pole Hledat na panelu nástrojů v [Průzkumníkovi XML](../xml-tools/xml-schema-explorer.md) zadejte "PurchaseOrder" a klikněte na tlačítko Hledat.

     ![Hledání klíčového slova Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearch.gif)

     Výsledky hledání jsou zvýrazněny v **Průzkumníku schémat XML** a označené značkami na svislém posuvníku.

3. Do pracovního prostoru přidejte výsledky hledání kliknutím na tlačítko **Přidat zvýrazněné uzly do pracovního prostoru** v podokně souhrnné výsledky.

     ![Výsledek hledání v Průzkumníkovi schémat XML](../xml-tools/media/schemaexplorersearchresult.gif)

     Uzel a uzel se zobrazí vedle sebe na návrhové ploše [zobrazení grafu.](../xml-tools/graph-view.md) `purchaseOrder` `PurchaseOrderType` Vzhledem k tomu, že oba uzly jsou `purchaseOrder` související (element je `PurchaseOrderType` typu), je mezi nimi vykreslena šipka.
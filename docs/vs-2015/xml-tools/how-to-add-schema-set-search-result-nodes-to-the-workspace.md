---
title: 'Postupy: přidání uzlů výsledků hledání v sadě schémat do pracovního prostoru | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 19157704019a949a4b2590ff277bcabd3bb320f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674648"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>Postupy: přidání uzlů výsledků hledání v sadě schémat do pracovního prostoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: přidání nastavení uzlů výsledků hledání schémat do pracovního prostoru](https://docs.microsoft.com/visualstudio/xml-tools/how-to-add-schema-set-search-result-nodes-to-the-workspace).  
  
  
Toto téma vysvětluje, jak přidat uzly, kteří jsou zvýrazněni v Průzkumník schémat XML jako výsledek hledání klíčového slova v pracovním prostoru.  
  
> [!NOTE]
>  Lze přidat pouze globální uzly [pracovní prostor](../xml-tools/xml-schema-designer-workspace.md).  
  
 Tento příklad používá ukázku [nákupní pořadí schématu](../xml-tools/sample-xsd-file-purchase-order-schema.md).  
  
### <a name="to-add-schema-set-result-nodes"></a>Přidání uzlů výsledků sadě schémat  
  
1.  Postupujte podle kroků v [postupy: vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
2.  Do textového pole hledání zadejte "purchaseOrder" [Průzkumník XML](../xml-tools/xml-schema-explorer.md) nástrojů a klikněte na tlačítko Hledat.  
  
     ![Hledání klíčových slov Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
     Výsledky hledání jsou zvýrazněné Průzkumníka schémat XML a označeny dílků na svislý posuvník.  
  
3.  Výsledky hledání do pracovního prostoru přidat kliknutím **přidá zvýrazněné uzly do pracovního prostoru** tlačítko na panelu souhrnu výsledků.  
  
     ![Výsledek hledání Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")  
  
     `purchaseOrder` Uzlu a `PurchaseOrderType` uzel se zobrazí vedle sebe na návrhové ploše [zobrazení grafu](../xml-tools/graph-view.md). Protože se týkají dva uzly ( `purchaseOrder` element má `PurchaseOrderType` typu), šipka vykreslením mezi nimi.




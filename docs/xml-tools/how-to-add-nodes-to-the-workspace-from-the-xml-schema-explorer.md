---
title: "Postupy: přidání uzlů do pracovního prostoru z Průzkumníka schématu XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b5a5749-9693-4b29-b0c2-8e07e0e55514
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 37da28d4c5db1e008af29c03997943720dcfbada
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer"></a>Postupy: přidání uzlů do pracovního prostoru z Průzkumníka schématu XML
Toto téma vysvětluje, jak přidat uzly do [Návrhář schématu XML prostoru](../xml-tools/xml-schema-designer-workspace.md) z Průzkumníka schématu XML. Toho lze dosáhnout pomocí přetahování uzlů z Průzkumníka schématu XML do zobrazení o návrháři XSD nebo pomocí místní nabídku Průzkumníka schématu XML. Můžete také přidat uzly, kteří jsou zvýrazněni v důsledku vyhledávání provádí Explorer schématu XML. Další informace najdete v tématu [postupy: přidání schématu nastavit vyhledávání výsledek uzly do pracovního prostoru](../xml-tools/how-to-add-schema-set-search-result-nodes-to-the-workspace.md).  
  
> [!NOTE]
>  Pouze globální uzly mohou být přidány do [prostoru Návrhář schématu XML](../xml-tools/xml-schema-designer-workspace.md).  
  
### <a name="to-add-nodes-through-the-xml-explorer-context-menu"></a>Chcete-li přidat uzly prostřednictvím místní nabídku Průzkumníka XML  
  
1.  Postupujte podle kroků v [postupy: vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
2.  Klikněte pravým tlačítkem na `PurchaseOrderType` uzlu Průzkumníku XSD. Vyberte **zobrazit v zobrazení grafu**.  
  
     `purchaseOrderType` Uzel se objeví na plochu návrháře zobrazení grafu.  
  
### <a name="to-drag-and-drop-a-node-on-to-a-view"></a>Přetáhnout uzel k zobrazení  
  
1.  Klikněte pravým tlačítkem na `PurchaseOrderType` uzel v zobrazení grafu. Vyberte **zobrazit v Průzkumníku schématu XML**.  
  
     Uzel je zvýrazněn v Průzkumníku schématu XML.  
  
2.  Klikněte pravým tlačítkem na `PurchaseOrderType` uzlu v Průzkumníku schématu XML a vyberte **zobrazit všechny odkazy**.  
  
     `purchaseOrder` Zvýrazní se uzel.  
  
3.  Přetáhněte `purchaseOrder` uzel k zobrazení grafu.  
  
     `purchaseOrder` Uzlu a `PurchaseOrderType` uzlu zobrazí vedle sebe na plochu návrháře zobrazení grafu. Vzhledem k tomu, že dva uzly jsou realted ( `purchaseOrder` element je `PurchaseOrderType` typu), šipka vykreslením mezi nimi.  
  
### <a name="to-add-nodes-using-the-schema-explorer-search-capability"></a>Přidání uzlů pomocí funkce vyhledávání Explorer schématu  
  
1.  Zadejte do vyhledávacího pole text "purchaseOrder" [XML Explorer](../xml-tools/xml-schema-explorer.md) panelu nástrojů a klikněte na tlačítko Hledat.  
  
     ![Hledání klíčových slov Explorer schématu XML](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
     Výsledky hledání jsou zvýrazněných v Průzkumníku schématu XML a označeny rysky svislém posuvníku.  
  
2.  Výsledky hledání přidat do pracovního prostoru kliknutím **přidat zvýrazněné uzly do pracovního prostoru** stisknutí tlačítka na panelu shrnutí výsledků.  
  
     ![Výsledek hledání Explorer schématu XML](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")  
  
     `purchaseOrder` Uzlu a `PurchaseOrderType` uzel se zobrazí vedle sebe na návrhové plochy [zobrazení grafu](../xml-tools/graph-view.md). Protože se vztahují dva uzly ( `purchaseOrder` element je `PurchaseOrderType` typu), šipka vykreslením mezi nimi.  
  
## <a name="see-also"></a>Viz také  
 [Průzkumník schémat XML](../xml-tools/xml-schema-explorer.md)
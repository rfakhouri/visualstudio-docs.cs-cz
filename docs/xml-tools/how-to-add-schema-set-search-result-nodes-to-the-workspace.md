---
title: "Postupy: přidání schématu sady vyhledávání výsledek uzlů do pracovního prostoru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 95b479a94d3d561541e0b33e710fddf55ecb71bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>Postupy: přidání schématu sady vyhledávání výsledek uzlů do pracovního prostoru
Toto téma vysvětluje, jak přidat uzly, kteří jsou zvýrazněni v Průzkumníku schématu XML jako výsledky hledání – klíčové slovo v pracovním prostoru.  
  
> [!NOTE]
>  Pouze globální uzly mohou být přidány do [prostoru](../xml-tools/xml-schema-designer-workspace.md).  
  
 Tento příklad používá vzorku [nákupu pořadí schématu](../xml-tools/sample-xsd-file-purchase-order-schema.md).  
  
### <a name="to-add-schema-set-result-nodes"></a>Chcete-li přidat schématu nastavit výsledek uzly  
  
1.  Postupujte podle kroků v [postupy: vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
2.  Zadejte do vyhledávacího pole text "purchaseOrder" [XML Explorer](../xml-tools/xml-schema-explorer.md) panelu nástrojů a klikněte na tlačítko Hledat.  
  
     ![Hledání klíčových slov Explorer schématu XML](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
     Výsledky hledání jsou zvýrazněných v Průzkumníku schématu XML a označeny rysky svislém posuvníku.  
  
3.  Výsledky hledání přidat do pracovního prostoru kliknutím **přidat zvýrazněné uzly do pracovního prostoru** stisknutí tlačítka na panelu shrnutí výsledků.  
  
     ![Výsledek hledání Explorer schématu XML](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")  
  
     `purchaseOrder` Uzlu a `PurchaseOrderType` uzel se zobrazí vedle sebe na návrhové plochy [zobrazení grafu](../xml-tools/graph-view.md). Protože se vztahují dva uzly ( `purchaseOrder` element je `PurchaseOrderType` typu), šipka vykreslením mezi nimi.
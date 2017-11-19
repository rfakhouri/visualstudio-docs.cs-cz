---
title: "Uložení datové sady ve formátu XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 1e41e0481325838b5de60b76ed1c7c1fc617f48e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="save-a-dataset-as-xml"></a>Uložení datové sady ve formátu XML
Při volání metody dostupné XML na datovou sadu můžete přístupu k datům XML v datové sadě. Chcete-li uložit data ve formátu XML, můžete zavolat buď <xref:System.Data.DataSet.GetXml%2A> metoda nebo <xref:System.Data.DataSet.WriteXml%2A> metodu <xref:System.Data.DataSet>.  
  
 Volání <xref:System.Data.DataSet.GetXml%2A> metoda vrátí řetězec, který obsahuje data ze všech tabulek dat v datové sadě, který je naformátovaný jako XML.  
  
 Volání <xref:System.Data.DataSet.WriteXml%2A> metoda odesílá data formátu XML do souboru, který zadáte.  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>Pro uložení dat v datové sadě jako XML proměnné  
  
-   <xref:System.Data.DataSet.GetXml%2A> Metoda vrátí <xref:System.String>. To znamená, že deklarujete proměnné typu <xref:System.String> a přiřaďte ho výsledky <xref:System.Data.DataSet.GetXml%2A> metoda.  
  
     [!code-vb[VbRaddataSaving#12](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_1.vb)]
     [!code-csharp[VbRaddataSaving#12](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_1.cs)]  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>Pro uložení dat v datové sadě jako XML do souboru  
  
-   <xref:System.Data.DataSet.WriteXml%2A> Metoda má několik přetížení. Následující kód ukazuje, jak uložit data do souboru. Deklarace proměnné a přiřaďte ho platnou cestu k uložení souboru do.  
  
     [!code-vb[VbRaddataSaving#13](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_2.vb)]
     [!code-csharp[VbRaddataSaving#13](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_2.cs)]  
  
## <a name="see-also"></a>Viz také  
 [Uložit data zpět do databáze](../data-tools/save-data-back-to-the-database.md)
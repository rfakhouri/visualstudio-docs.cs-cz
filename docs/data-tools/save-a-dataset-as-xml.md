---
title: Uložení datové sady ve formátu XML
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: c1eff1b80807b040bd50d7e4e5f2045c73c46929
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55011816"
---
# <a name="save-a-dataset-as-xml"></a>Uložení datové sady ve formátu XML

Přístup k datům XML v datové sadě voláním dostupné metody XML v datové sadě. K ukládání dat ve formátu XML, lze volat buď <xref:System.Data.DataSet.GetXml%2A> metoda nebo <xref:System.Data.DataSet.WriteXml%2A> metodu <xref:System.Data.DataSet>.

Volání <xref:System.Data.DataSet.GetXml%2A> metoda vrátí řetězec, který obsahuje data ze všech tabulek dat v datové sadě, který je formátován jako XML.

Volání <xref:System.Data.DataSet.WriteXml%2A> metoda odesílá data ve formátu XML do souboru, který zadáte.

## <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>Chcete-li uložit data v datové sadě ve formátu XML do proměnné

- <xref:System.Data.DataSet.GetXml%2A> Metoda vrátí hodnotu <xref:System.String>. Deklarovat proměnnou typu <xref:System.String> a přiřaďte ho výsledky <xref:System.Data.DataSet.GetXml%2A> metody.

     [!code-vb[VbRaddataSaving#12](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_1.vb)]
     [!code-csharp[VbRaddataSaving#12](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_1.cs)]

## <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>Chcete-li uložit data v datové sadě ve formátu XML do souboru

- <xref:System.Data.DataSet.WriteXml%2A> Metoda má několik přetížení. Deklarujte proměnnou a přiřaďte ho platnou cestu k uložení souboru. Následující kód ukazuje, jak uložit data do souboru:

     [!code-vb[VbRaddataSaving#13](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_2.vb)]
     [!code-csharp[VbRaddataSaving#13](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_2.cs)]

## <a name="see-also"></a>Viz také:

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)
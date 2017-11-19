---
title: "Postupy: mapování schémat na listy v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML schemas [Office development in Visual Studio], mapping
- mappings [Office development in Visual Studio], XML schemas to Excel worksheets
- Excel [Office development in Visual Studio], XML schemas
- worksheets [Office development in Visual Studio], XML schemas
ms.assetid: cef3f751-c1cf-46f3-9177-0bacdcee4121
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c09c99bc5d8bc964ae3afd82fe7a4a9fd5764edd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-map-schemas-to-worksheets-inside-visual-studio"></a>Postupy: Mapování schémat na listy v prostředí Visual Studio
  Do listu můžete namapovat schématu XML listu je otevřen v sadě Visual Studio. Můžete použít stejné nástroje Microsoft Office Excel, které používáte, když je sešit otevřít mimo Visual Studio. Microsoft Office project vytvoří stejné objekty, zda mapování schématu na listu před nebo po vytvoření řešení aplikace Excel.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  V řešení pro aplikaci Excel nelze použít s více částmi schémat XML.  
  
### <a name="to-map-an-xml-schema-to-an-excel-worksheet-in-visual-studio"></a>Pro mapování schématu XML listu aplikace Excel v sadě Visual Studio  
  
1.  Otevřete projekt sešitu nebo šablony aplikace Excel v sadě Visual Studio.  
  
2.  Klepněte na listu přesunout fokus na návrháře.  
  
3.  Na pásu karet klikněte na **vývojáře** kartě.  
  
    > [!NOTE]  
    >  Pokud **vývojáře** karta není viditelný, musíte ji nejdříve zobrazit. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
4.  V **XML** klikněte na možnost **zdroj**.  
  
     **Zdroj dat XML** otevře se okno.  
  
5.  V **zdroj dat XML** okně klikněte na tlačítko **mapování XML**.  
  
     **Mapování XML** otevře se dialogové okno.  
  
6.  V **mapování XML** dialogové okno, klikněte na tlačítko **přidat**.  
  
7.  Přejděte do souboru schématu, vyberte ho a pak klikněte na tlačítko **otevřete**.  
  
8.  Click **OK**.  
  
     Schéma je znázorněná **zdroj dat XML** okno. Ve vašem projektu typové <xref:System.Data.DataSet> se vygeneruje na základě schématu a <xref:System.Windows.Forms.BindingSource> je vytvořena.  
  
9. Přetáhněte elementy z **zdroj dat XML** okno na místa v sešitě, kde chcete vytvořit odpovídající ovládací prvky.  
  
     Přetáhnete element schématu bez opakování, Microsoft Office project generuje <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládací prvek, který je automaticky vázána <xref:System.Windows.Forms.BindingSource>.  
  
     Přetažením opakující se prvek schématu generuje Microsoft Office project <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který není vázán automaticky ke zdroji dat. Další informace najdete v tématu [schémat XML a Data v přizpůsobeních na úrovni dokumentu](../vsto/xml-schemas-and-data-in-document-level-customizations.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: mapování schémat na dokumenty aplikace Word v sadě Visual Studio](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [Schémata XML a Data v přizpůsobeních na úrovni dokumentu](../vsto/xml-schemas-and-data-in-document-level-customizations.md)  
  
  
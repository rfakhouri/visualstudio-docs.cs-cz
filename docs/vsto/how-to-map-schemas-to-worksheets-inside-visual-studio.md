---
title: 'Postupy: Mapování schémat na listy v prostředí Visual Studio'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML schemas [Office development in Visual Studio], mapping
- mappings [Office development in Visual Studio], XML schemas to Excel worksheets
- Excel [Office development in Visual Studio], XML schemas
- worksheets [Office development in Visual Studio], XML schemas
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 672acf2b33463ee5110dc537f14831a1c034380e
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53646651"
---
# <a name="how-to-map-schemas-to-worksheets-inside-visual-studio"></a>Postupy: Mapování schémat na listy v prostředí Visual Studio
  Můžete namapovat schématu XML listu listu je otevřen v sadě Visual Studio. Můžete používat stejné nástroje Microsoft Office Excel, které používáte, pokud se sešit otevřít mimo sadu Visual Studio. Office project vytvoří stejné objekty, zda mapování schématu do listu před nebo po vytvoření řešení pro Excel.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  V řešení pro aplikaci Excel nelze použít s více částmi schémat XML.  
  
## <a name="to-map-an-xml-schema-to-an-excel-worksheet-in-visual-studio"></a>K mapování schématu XML listu aplikace Excel v sadě Visual Studio  
  
1.  Otevřete Excelový sešit nebo šablonu projektu v sadě Visual Studio.  
  
2.  Klepněte na listu přesunout fokus do návrháře.  
  
3.  Na pásu karet klikněte na tlačítko **Developer** kartu.  
  
    > [!NOTE]  
    >  Pokud **Developer** karta není zobrazena, musíte ji nejdříve zobrazit. Další informace najdete v tématu [jak: Zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
4.  V **XML** klikněte na možnost **zdroj**.  
  
     **XML použitého jako zdroj** otevře se okno.  
  
5.  V **XML použitého jako zdroj** okna, klikněte na tlačítko **mapování XML**.  
  
     **Mapování XML** zobrazí se dialogové okno.  
  
6.  V **mapování XML** dialogové okno, klikněte na tlačítko **přidat**.  
  
7.  Přejděte do souboru schématu, vyberte ji a pak klikněte na tlačítko **otevřít**.  
  
8.  Klikněte na **OK**.  
  
     Schéma je vyjádřena v **XML použitého jako zdroj** okna. Ve vašem projektu, typovaného <xref:System.Data.DataSet> je generován a základě schématu a <xref:System.Windows.Forms.BindingSource> se vytvoří.  
  
9. Prvky z přetáhnout **XML použitého jako zdroj** okno na místa v listu, kde chcete vytvořit odpovídající ovládací prvky.  
  
     Pokud přetáhnete na prvek schématu neopakujícími generuje Office project <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládací prvek, který je automaticky vázán na <xref:System.Windows.Forms.BindingSource>.  
  
     Pokud přetáhnete opakující se element schématu generuje projekt sady Office <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který není automaticky svázán se zdrojem dat. Další informace najdete v tématu [schémat XML a data v úrovni dokumentu přizpůsobení](../vsto/xml-schemas-and-data-in-document-level-customizations.md).  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Mapování schémat na dokumenty aplikace Word v sadě Visual Studio](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [Schémata XML a data v přizpůsobeních na úrovni dokumentu](../vsto/xml-schemas-and-data-in-document-level-customizations.md)  
  
  
---
title: "Ovládacích prvků na listech aplikace Excel pomocí Windows Forms. | Microsoft Docs"
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
- Windows Forms controls [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], Window Forms controls
ms.assetid: bbda7461-0d69-4b56-8ba3-418d63ba49db
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3d80158853ec042b98f7e40feda70520af55ed32
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-windows-forms-controls-on-excel-worksheets"></a>Použití ovládacích prvků Windows Forms na listech aplikace Excel
  Windows Forms – ovládací prvky můžete přidat do vaší aplikace Microsoft Office Excel sešitů stejným způsobem jako přidávání ovládacích prvků do formulářů Windows. Obecné informace o práci s ovládacími prvky v dokumentech najdete v tématu [ovládacích prvků Windows Forms na přehled dokumenty Office](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="control-considerations-for-excel"></a>Důležité informace o řízení pro aplikaci Excel  
 Existuje několik aspekty, které jsou specifické pro aplikaci Excel.  
  
### <a name="matching-control-size-to-cell-size"></a>Buňka velikost odpovídající velikost ovládacího prvku  
 Můžete nastavit na změnu velikosti automaticky při změně velikosti nadřazené buňce ovládacího prvku. Další informace najdete v tématu [postupy: Změna velikosti ovládacích prvků v buňkách listu](../vsto/how-to-resize-controls-within-worksheet-cells.md).  
  
### <a name="adding-components-that-are-shared-by-all-worksheets"></a>Přidávání součástí, které jsou sdíleny všech listů  
 Můžete přidat součásti, které chcete sdílet mezi všechny listy, například <xref:System.Data.DataSet>, k sešitu Designer místo do listů. Součást se zobrazí na panelu součásti.  
  
### <a name="formula-for-embedding-controls"></a>Vzorec pro vložení ovládacích prvků  
 Když vyberete ovládacího prvku v aplikaci Excel, uvidíte **=EMBED("WinForms.Control.Host","")** v **řádek vzorců**. Tento text je nezbytné a nesmí být odstraněna.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Změna velikosti ovládacích prvků v buňkách listu](../vsto/how-to-resize-controls-within-worksheet-cells.md)   
 [Postupy: skrytí ovládacích prvků na listech při tisku](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [Návod: Změna formátování listů s použitím ovládacích prvků CheckBox](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)   
 [Návod: Zobrazení textu v textovém poli na listu s použitím tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)   
 [Návod: Aktualizace grafu na listu s použitím přepínačů](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md)  
  
  
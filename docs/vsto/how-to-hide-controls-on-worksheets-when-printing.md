---
title: 'Postupy: Skrytí ovládacích prvků na listech při tisku'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- printing [Office development in Visual Studio], worksheets
- controls [Office development in Visual Studio], hiding while printing
- printing [Office development in Visual Studio], hiding controls
- worksheets, hiding controls when printing
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: d245e6d1d4af1d0135abe88c89f54490a0f5296e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53873428"
---
# <a name="how-to-hide-controls-on-worksheets-when-printing"></a>Postupy: Skrytí ovládacích prvků na listech při tisku
  Při tisku dokumentu aplikace Microsoft Office Excel, který obsahuje ovládací prvky Windows Forms, ovládací prvky jsou viditelné na tisk listů. Ovládací prvky lze skrýt při tisku na listu.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  Pokud skrýt ovládací prvky, které zobrazují data, například <xref:Microsoft.Office.Tools.Excel.Controls.TextBox>, nebudou viditelné v tištěné listu dat v ovládacím prvku.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="to-hide-controls-when-a-worksheet-is-printed"></a>Chcete-li skrýt ovládací prvky, pokud list vytisknout  
  
1.  Vytvoření nebo otevření projektu aplikace Excel v sadě Visual Studio a ověřte, že **List1** je zobrazen v návrháři. Informace o vytváření projektů, naleznete v tématu [jak: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Z **běžné ovládací prvky** karty **nástrojů**, přetáhněte <xref:Microsoft.Office.Tools.Excel.Controls.Button> ovládací prvek buňky v `Sheet1`.  
  
3.  V **vlastnosti** okno, nastaveno <xref:Microsoft.Office.Tools.Excel.Controls.Button.PrintObject%2A> vlastnost **False**.  
  
## <a name="see-also"></a>Viz také:  
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Ovládací prvky Windows Forms na dokumenty Office – přehled](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Postupy: Přidání ovládacích prvků Windows Forms do dokumentů Office](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Postupy: Změna velikosti ovládacích prvků v buňkách listu](../vsto/how-to-resize-controls-within-worksheet-cells.md)  

---
title: "Postupy: skrytí ovládacích prvků na listech při tisku | Microsoft Docs"
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
- printing [Office development in Visual Studio], worksheets
- controls [Office development in Visual Studio], hiding while printing
- printing [Office development in Visual Studio], hiding controls
- worksheets, hiding controls when printing
ms.assetid: a637fe9a-9de1-4162-8ff6-fe28ccd62389
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 17ebd691120d1d5aba2623f8178d95c3fc142dee
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hide-controls-on-worksheets-when-printing"></a>Postupy: Skrytí ovládacích prvků na listech při tisku
  Při tisku dokumentu aplikace Microsoft Office Excel, který obsahuje ovládací prvky Windows Forms, ovládací prvky jsou viditelné na tištěných listu. Ovládací prvky můžete skrýt, při tisku na listu.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  Pokud jste skrytí ovládacích prvků, které zobrazují data, jako například <xref:Microsoft.Office.Tools.Excel.Controls.TextBox>, dat v ovládacím prvku nebude zobrazovat na tištěných listu.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-hide-controls-when-a-worksheet-is-printed"></a>Skrytí ovládacích prvků při list vytisknout  
  
1.  Vytvořit nebo otevřít projekt aplikace Excel v sadě Visual Studio a ověřte, že **Sheet1** se zobrazí v návrháři. Informace o vytváření projektů najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte ji <xref:Microsoft.Office.Tools.Excel.Controls.Button> na buňku řízení na `Sheet1`.  
  
3.  V **vlastnosti** nastavte <xref:Microsoft.Office.Tools.Excel.Controls.Button.PrintObject%2A> vlastnost **False**.  
  
## <a name="see-also"></a>Viz také  
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Windows Forms – ovládací prvky na přehled dokumenty sady Office](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Postupy: Přidání ovládacích prvků do dokumentů Office Windows Forms](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Postupy: Změna velikosti ovládacích prvků v buňkách listu](../vsto/how-to-resize-controls-within-worksheet-cells.md)  
  
  
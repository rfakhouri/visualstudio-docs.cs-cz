---
title: 'Postupy: Přidání Spouštěče dialogového okna do skupiny pásu karet'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- dialog box launcher [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], dialog box launcher
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: f6ec94b8fc170f195b00a6c093605860c97048ed
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53648694"
---
# <a name="how-to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>Postupy: Přidání Spouštěče dialogového okna do skupiny pásu karet
  Spouštěče dialogového okna můžete přidat do jakékoli skupiny na pásu karet. Spouštěče dialogového okna je malá ikona, která se zobrazí ve skupině. Uživatelé kliknou na tuto ikonu otevře související dialogová okna ani podokna úloh, které poskytují další možnosti, které se vztahují ke skupině.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>Přidání Spouštěče dialogového okna do skupiny pásu karet  
  
1.  Vyberte soubor kódu pásu karet (*.vb* nebo *.cs* souborů) v **Průzkumníka řešení**.  
  
2.  Na **zobrazení** nabídky, klikněte na tlačítko **návrháře**.  
  
3.  V Návrháři pásu karet klikněte pravým tlačítkem na libovolnou skupinu a potom klikněte na tlačítko **přidat DialogBoxLauncher**.  
  
     Přidejte kód, který <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup.DialogLauncherClick> události skupinu, kterou chcete otevřít vlastní nebo předdefinovaný dialogové okno.  
  
## <a name="see-also"></a>Viz také:  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Ukázky vývoje pro Office a názorné postupy](../vsto/office-development-samples-and-walkthroughs.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md)   
 [Pás karet – XML](../vsto/ribbon-xml.md)   
 [Postupy: Export pásu karet z Návrháře pásu karet na pásu karet XML](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Postupy: Změna umístění karty na pásu karet](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)   
 [Postupy: Přidání ovládacích prvků do zobrazení backstage](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Přizpůsobte pás karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Postupy: Zobrazení doplňku uživatele chyb rozhraní](../vsto/how-to-show-add-in-user-interface-errors.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Aktualizace ovládacích prvků na pásu karet za běhu](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  
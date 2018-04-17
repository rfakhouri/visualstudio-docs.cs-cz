---
title: Přístup k pásu karet za běhu | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Globals class, Ribbon
- Ribbon [Office development in Visual Studio], accessing
- RibbonManager class
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a6129779b66406ffe24dbe65e03b289cb917c1ae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="accessing-the-ribbon-at-run-time"></a>Přístup k pásu karet za běhu
  Můžete napsat kód pro zobrazení, skrytí a upravit na pásu karet a povolit uživatelům spustit kód z ovládacích prvků v vlastního podokna úloh, podokna akce nebo oblasti formuláře aplikace Outlook.  

 Máte přístup k pásu karet pomocí `Globals` třídy. Pro aplikaci Outlook projekty dostanete pásů karet, které se zobrazují v konkrétní okno Kontrola aplikace Outlook nebo v Průzkumníku aplikace Outlook.  

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  

## <a name="accessing-the-ribbon-by-using-the-globals-class"></a>Přístup k pásu karet pomocí Globals – třída  
 Můžete použít `Globals` třídy pro přístup k pásu karet v projektech na úrovni dokumentu nebo v projektu doplňku VSTO z libovolného místa v projektu.  

 Další informace o `Globals` třídy najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  

 Následující příklad používá `Globals` třídy pro přístup k vlastní pás karet s názvem `Ribbon1` a nastavit text, který se zobrazí na pole se seznamem na pásu karet `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#4](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#4)]
 [!code-csharp[Trin_Outlook_FR_Access#4](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#4)]  

## <a name="accessing-a-collection-of-ribbons-that-appear-in-a-specific-outlook-inspector-window"></a>Přístup ke kolekci pásů karet, které se zobrazují v okně kontroly konkrétní aplikace  
 Dostanete kolekce pásů karet, které se zobrazují v aplikaci Outlook *inspektoři*. Kontrolor je okno, které se otevře v aplikaci Outlook, když uživatelé provádět určité úlohy, jako je například vytváření e-mailových zpráv. Chcete-li získat přístup k pásu karet okně kontroly, volejte `Ribbons` vlastnost `Globals` třídy a předat <xref:Microsoft.Office.Interop.Outlook.Inspector> objekt, který představuje funkci Kontrola.  

 Následující příklad načte kolekci pásu karet Inspector, který má právě fokus. Tento příklad následně přistupuje k pásu karet s názvem `Ribbon1` a nastaví text, který se zobrazí na pole se seznamem na pásu karet `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#5](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#5)]
 [!code-csharp[Trin_Outlook_FR_Access#5](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#5)]  

## <a name="accessing-a-collection-of-ribbons-that-appear-for-a-specific-outlook-explorer"></a>Přístup ke kolekci pásů karet, které se zobrazují pro konkrétní aplikace Outlook Explorer  
 Dostanete kolekce pásů karet, které se zobrazují v aplikace Outlook *Explorer*. Je Explorer hlavní aplikace uživatelské rozhraní (UI) pro instance aplikace Outlook. Chcete-li získat přístup k pásu karet okno Průzkumníka, zavolejte `Ribbons` vlastnost `Globals` třídy a předat <xref:Microsoft.Office.Interop.Outlook.Explorer> objekt, který reprezentuje Průzkumníku.  

 Následující příklad načte kolekci pásu karet Explorer, který má právě fokus. Tento příklad následně přistupuje k pásu karet s názvem `Ribbon1` a nastaví text, který se zobrazí na pole se seznamem na pásu karet `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#6](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#6)]
 [!code-csharp[Trin_Outlook_FR_Access#6](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#6)]  

## <a name="see-also"></a>Viz také  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Kódu XML pásu karet](../vsto/ribbon-xml.md)   
 [Přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Aktualizace ovládacích prvků na pásu karet za běhu](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)  

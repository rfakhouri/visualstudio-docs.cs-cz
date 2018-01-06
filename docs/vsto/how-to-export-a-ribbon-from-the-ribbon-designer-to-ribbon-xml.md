---
title: "Postupy: Export pásu karet z Návrháře pásu karet do kódu XML pásu karet | Microsoft Docs"
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
- custom Ribbon, XML
- customizing the Ribbon, XML
- Ribbon [Office development in Visual Studio], XML
- Ribbon [Office development in Visual Studio], exporting
- XML [Office development in Visual Studio], Ribbon
- Ribbon Designer [Office development in Visual Studio]
- exporting Ribbon
ms.assetid: 96e0e9ed-4392-4f45-ac33-b6f7c22ea321
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d7cbdf38b3debd7710ed036d008d52b8ef080d37
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Postupy: Export pásu karet z návrháře pásu karet do kódu XML pásu karet
  **Pásu karet (vizuálního návrháře)** položku nepodporuje všechny možné typy přizpůsobení pásu karet. Přizpůsobení pásu karet pokročilé způsoby, můžete exportovat na pásu karet z Návrháře do kódu XML pásu karet a přímo upravit soubor XML.  
  
> [!NOTE]  
>  Ne všechny hodnoty vlastností se zobrazí v souboru XML pásu karet. Další informace najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Export pásu karet z Návrháře pásu karet do kódu XML pásu karet  
  
1.  Klikněte pravým tlačítkem na pásu karet souboru kódu v **Průzkumníku řešení**a potom klikněte na **Návrhář zobrazení**.  
  
2.  Klikněte pravým tlačítkem na Návrháře pásu karet a pak klikněte na **Export pásu karet na XML**.  
  
     Visual Studio přidá soubor XML pásu karet a soubor kódu XML pásu karet do projektu.  
  
3.  Ve třídě kódu pásu karet najděte komentáře, které začínají `TODO:`.  
  
4.  Zkopírujte blok kódu v těchto komentáře **ThisAddin**, **ThisWorkbook**, nebo **ThisDocument** třídy, v závislosti na tom, jaký typ řešení vyvíjíte.  
  
     Tento kód umožňuje aplikaci Microsoft Office ke zjištění a načíst vaše vlastní pás karet. Další informace najdete v tématu [XML karet](../vsto/ribbon-xml.md).  
  
5.  V **ThisAddin**, **ThisWorkbook**, nebo **ThisDocument** třídy, zrušte komentář kódu bloku.  
  
     Po zrušte komentář u kód by měl podobat následujícímu příkladu. V tomto příkladu je volána třída pásu karet `MyRibbon`.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]  
  
6.  Přepněte do souboru kódu XML pásu karet a najít `Ribbon Callbacks` oblast.  
  
     Toto je, kde můžete psát metody zpětného volání pro zpracování akce uživatele, například kliknutí na tlačítko.  
  
7.  Vytvoření metody zpětného volání pro každou obslužnou rutinu události, který jste napsali v kódu Návrhář pásu karet.  
  
8.  Přesunout všechny kód obslužné rutiny události z obslužné rutiny událostí do metody zpětného volání a upravte kód pro práci s programovací model rozšiřitelnosti pásu karet (RibbonX).  
  
     Informace o psaní metody zpětného volání a pomocí programovacího modelu RibbonX najdete v tématu [XML karet](../vsto/ribbon-xml.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Kódu XML pásu karet](../vsto/ribbon-xml.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  
---
title: "Globální přístup k objektům v projektech Office | Microsoft Docs"
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
- ThisDocument_Shutdown
- ThisDocument_Startup
- Globals class, object global access
- worksheets [Office development in Visual Studio], global access
- documents [Office development in Visual Studio], global access
- event handlers [Office development in Visual Studio]
- ThisWorkbook_Startup
- application-level addins [Office development in Visual Studio]
- addins [Office development in Visual Studio], events
- workbooks [Office development in Visual Studio], global access
- ThisWorkbook_Shutdown
- document-level customizations [Office development in Visual Studio]
- Startup event
- Shutdown event
- projects [Office development in Visual Studio], global access
- Office documents [Office development in Visual Studio, global access
- ThisAddin_Startup
- events [Office development in Visual Studio]
- ThisAddIn_Shutdown
ms.assetid: f6a7f0ef-75d0-4a9b-9aec-be95ffa26adf
caps.latest.revision: "55"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c8119ccf0c6715d1c18957fcf8cac92d9872a27e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="global-access-to-objects-in-office-projects"></a>Globální přístup k objektům v projektech pro systém Office
  Když vytvoříte projekt Office, Visual Studio automaticky vygeneruje třídy s názvem `Globals` v projektu. Můžete použít `Globals` třídy pro přístup k několika jiný projekt položky v době běhu z jakékoli kódu v projektu.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="how-to-use-the-globals-class"></a>Jak používat Globals – třída  
 `Globals`je statická třída, která uchovává odkazy na některé položky ve vašem projektu. Pomocí `Globals` třída, dostanete následující položky z jakékoli kódu v projektu v době běhu:  
  
-   `ThisWorkbook` a `Sheet`  *n*  třídy v sešitu nebo šablony projektu aplikace Excel. Máte přístup k těmto objektům pomocí `Globals.ThisWorkbook` a `Sheet`  *n*  vlastnosti.  
  
-   `ThisDocument` – Třída v dokumentu nebo šablony projektu aplikace Word. Máte přístup k tomuto objektu pomocí `Globals.ThisDocument` vlastnost.  
  
-   `ThisAddIn` – Třída v projektu doplňku VSTO. Máte přístup k tomuto objektu pomocí `Globals.ThisAddIn` vlastnost.  
  
-   Všechny pásů karet ve vašem projektu, který jste si přizpůsobili pomocí Návrháře pásu karet. Máte přístup k pásů karet pomocí `Globals.Ribbons` vlastnost. Další informace najdete v tématu [přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md).  
  
-   Všechny oblastí formulářů aplikace Outlook v projektu doplňku VSTO v Outlooku. Máte přístup k oblasti formuláře pomocí `Globals.FormRegions` vlastnost. Další informace najdete v tématu [přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md).  
  
-   Objekt factory, která umožňuje vytvářet ovládacích prvků pásu karet a hostitele položky v době běhu v projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Máte přístup k tomuto objektu pomocí `Globals.Factory` vlastnost. Tento objekt je instance třídy, která implementuje jedno rozhraní následující:  
  
    -   <xref:Microsoft.Office.Tools.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Excel.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Outlook.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Word.Factory>  
  
 Například můžete použít `Globals.Sheet1` vlastnost vložit text do <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení na `Sheet1` když uživatel klikne tlačítko v podokně Akce v projektech na úrovni dokumentu pro Excel.  
  
 [!code-vb[Trin_VstcoreProgramming#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/Sheet1.vb#1)]
 [!code-csharp[Trin_VstcoreProgramming#1](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/Sheet1.cs#1)]  
  
## <a name="initializing-the-globals-class"></a>Inicializace Globals – třída  
 Kód, který se pokouší použít `Globals` výjimku době běhu může vyvolat třída před dokumentu nebo doplňku VSTO je zcela inicializován. Například pomocí `Globals` při deklarace proměnné úrovni třídy nemusí podařit, protože `Globals` – třída nemusí být inicializovaný s odkazy na všechny hostitele položky předtím, než dojde k vytvoření deklarované objektu.  
  
> [!NOTE]  
>  `Globals` Nikdy inicializaci třídy v době návrhu, ale ovládací prvek instance jsou vytvořené pomocí návrháře. To znamená, že pokud vytvoříte uživatelský ovládací prvek, který používá vlastnost `Globals` třída ze uvnitř třídu uživatelského ovládacího prvku, je třeba jestli vlastnost vrací **null** předtím, než se pokusíte použít vráceného objektu.  
  
## <a name="see-also"></a>Viz také  
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Hostitelská položka Document](../vsto/document-host-item.md)   
 [Hostitelská položka Workbook](../vsto/workbook-host-item.md)   
 [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)  
  
  
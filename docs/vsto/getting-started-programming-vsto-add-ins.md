---
title: "Začínáme programováním doplňků VSTO | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.ProjectItem.Outlook
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], getting started
- add-ins [Office development in Visual Studio], getting started
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: f395ce7fb85d71ed6e8c3f7dfb10726907832873
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="getting-started-programming-vsto-add-ins"></a>Začínáme s programováním doplňků VSTO
  Doplňků VSTO slouží k automatizaci aplikace Microsoft Office, rozšířit funkce aplikace a přizpůsobení uživatelského rozhraní (UI) aplikace. Informace o tom, jak porovnat doplňků VSTO na jiné typy řešení pro systém Office, můžete vytvořit pomocí sady Visual Studio najdete v tématu [přehled vývoje řešení pro systém Office & #40; VSTO & #41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
## <a name="creating-vsto-add-in-projects"></a>Vytváření projekty doplňku VSTO  
 Vytvořit pomocí jedné z šablon projektu doplňku VSTO v projekty doplňku VSTO **nový projekt** dialogové okno. Tyto šablony zahrnout požadované odkazy na sestavení a soubory projektu. Visual Studio poskytuje šablony projektu doplňku VSTO pro většinu aplikací v sadě Office.  
  
 Další informace o tom, jak vytvořit projekt VSTO Add-in najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md). Další informace o šablonách projektů najdete v tématu [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md).  
  
## <a name="developing-vsto-add-in-projects"></a>Vývoj projekty doplňku VSTO  
 Při vytváření projektu doplňku VSTO Visual Studio automaticky vytvoří ThisAddIn.vb (v [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) nebo souboru kódu ThisAddIn.cs (v jazyku C#). Tento soubor obsahuje `ThisAddIn` třídy, která poskytuje základ pro vaše doplňku VSTO. Členy této třídy můžete použít ke spuštění kódu v doplňku VSTO načtení či odpojeno, přístup k modelu objektu hostitelské aplikace a rozšířit funkce aplikace. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
## <a name="automating-applications-by-using-the-object-models"></a>Automatizace aplikací pomocí objektové modely  
 Objektové modely z aplikace Microsoft Office vystavit mnoho typů, které můžete naprogramovat oproti v doplňku VSTO. Tyto typy můžete použít k automatizaci aplikace. Například prostřednictvím kódu programu můžete vytvořit a odeslat e-mailovou zprávu v Outlooku, nebo můžete otevřít dokument a přidat obsahu v aplikaci Word. Další informace o tom, jak přístup k modelu objektu hostitelské aplikace v kódu najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
 Další informace o objektu modely konkrétní aplikace Microsoft Office najdete v následujících tématech:  
  
-   [Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)  
  
-   [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)  
  
-   [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)  
  
-   [InfoPath – řešení](../vsto/infopath-solutions.md)  
  
-   [Řešení pro aplikaci PowerPoint](../vsto/powerpoint-solutions.md)  
  
-   [Projektová řešení](../vsto/project-solutions.md)  
  
-   [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)  
  
## <a name="customizing-the-user-interface-of-applications"></a>Přizpůsobení uživatelského rozhraní aplikace  
 Přizpůsobení uživatelského rozhraní aplikace hostitele pomocí doplňku VSTO několika různými způsoby:  
  
-   Pro aplikaci Excel a Word můžete přidat spravovaných ovládacích prvků do dokumentů. Další informace najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
-   Pokud aplikace podporuje, můžete upravit na pásu karet. Další informace najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
-   Pokud aplikace podporuje, můžete vytvořit vlastního podokna úloh. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
-   Pro aplikaci Outlook můžete vytvořit vlastní formulář oblast. Další informace najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
-   Pro všechny aplikace Microsoft Office můžete zobrazit Windows Forms v doplňku VSTO.  
  
 Další informace o tom, jak přizpůsobit aplikace uživatelského rozhraní aplikace Microsoft Office, najdete v části [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
## <a name="next-steps"></a>Další kroky  
 Informace o vytváření doplňků VSTO, najdete na následující kurzy:  
  
-   [Návod: Vytvoření prvního doplňku VSTO pro Excel](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)  
  
-   [Návod: Vytvoření prvního doplňku VSTO pro Outlook](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)  
  
-   [Návod: Vytvoření prvního doplňku VSTO pro PowerPoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)  
  
-   [Návod: Vytvoření prvního doplňku VSTO pro Project](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)  
  
-   [Návody: Vytvoření prvního doplňku VSTO pro Word](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)  
  
 Tyto postupy vám představí vývojových nástrojů Office v sadě Visual Studio a programovací model pro doplňky VSTO.  
  
 Seznam témat, která vás provede procesem některé běžné úlohy v projektech Office najdete v tématu [běžné úlohy při programování Office](../vsto/common-tasks-in-office-programming.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Začínáme & #40; vývoj pro Office v sadě Visual Studio & #41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)  
  
  
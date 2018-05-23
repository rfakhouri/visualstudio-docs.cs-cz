---
title: Začínáme s programováním doplňků VSTO
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7249c3971c8008f70b9e5add79adddde17fe6a82
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="get-started-programming-vsto-add-ins"></a>Začínáme s programováním doplňků VSTO
  Doplňků VSTO slouží k automatizaci aplikace Microsoft Office, rozšířit funkce aplikace a přizpůsobení uživatelského rozhraní (UI) aplikace. Informace o tom, jak porovnat doplňků VSTO na jiné typy řešení pro systém Office, můžete vytvořit pomocí sady Visual Studio najdete v tématu [přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
## <a name="create-vsto-add-in-projects"></a>Vytvořit projekty doplňku VSTO  
 Vytvořit pomocí jedné z šablon projektu doplňku VSTO v projekty doplňku VSTO **nový projekt** dialogové okno. Tyto šablony zahrnout požadované odkazy na sestavení a soubory projektu. Visual Studio poskytuje šablony projektu doplňku VSTO pro většinu aplikací v sadě Office.  
  
 Další informace o tom, jak vytvořit projekt VSTO Add-in najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md). Další informace o šablonách projektů najdete v tématu [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md).  
  
## <a name="develop-vsto-add-in-projects"></a>Vyvíjet projekty doplňku VSTO  
 Při vytváření projektu doplňku VSTO Visual Studio automaticky vytvoří *ThisAddIn.vb* (v [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) nebo *ThisAddIn.cs* (v jazyku C#) kódu souboru. Tento soubor obsahuje `ThisAddIn` třídy, která poskytuje základ pro vaše doplňku VSTO. Členy této třídy můžete použít ke spuštění kódu v doplňku VSTO načtení či odpojeno, přístup k modelu objektu hostitelské aplikace a rozšířit funkce aplikace. Další informace najdete v tématu [Program VSTO doplňků](../vsto/programming-vsto-add-ins.md).  
  
## <a name="automate-applications-by-using-the-object-models"></a>Automatizace aplikace pomocí objektové modely  
 Objektové modely z aplikace Microsoft Office vystavit mnoho typů, které můžete naprogramovat oproti v doplňku VSTO. Tyto typy můžete použít k automatizaci aplikace. Například prostřednictvím kódu programu můžete vytvořit a odeslat e-mailovou zprávu v Outlooku, nebo můžete otevřít dokument a přidat obsahu v aplikaci Word. Další informace o tom, jak přístup k modelu objektu hostitelské aplikace v kódu najdete v tématu [Program VSTO doplňků](../vsto/programming-vsto-add-ins.md).  
  
 Další informace o objektu modely konkrétní aplikace Microsoft Office najdete v následujících tématech:  
  
-   [Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)  
  
-   [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)  
  
-   [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)  
  
-   [Řešení pro aplikaci InfoPath](../vsto/infopath-solutions.md)  
  
-   [Řešení pro aplikaci PowerPoint](../vsto/powerpoint-solutions.md)  
  
-   [Projektová řešení](../vsto/project-solutions.md)  
  
-   [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)  
  
## <a name="customize-the-user-interface-of-applications"></a>Přizpůsobení uživatelského rozhraní aplikací  
 Přizpůsobení uživatelského rozhraní aplikace hostitele pomocí doplňku VSTO několika různými způsoby:  
  
-   Pro aplikaci Excel a Word můžete přidat spravovaných ovládacích prvků do dokumentů. Další informace najdete v tématu [dokumentů rozšířit aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
-   Pokud aplikace podporuje, můžete upravit na pásu karet. Další informace najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
-   Pokud aplikace podporuje, můžete vytvořit vlastního podokna úloh. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
-   Pro aplikaci Outlook můžete vytvořit vlastní formulář oblast. Další informace najdete v tématu [oblastí formulářů aplikace Outlook vytvořit](../vsto/creating-outlook-form-regions.md).  
  
-   Pro všechny aplikace Microsoft Office můžete zobrazit Windows Forms v doplňku VSTO.  
  
 Další informace o tom, jak přizpůsobit aplikace uživatelského rozhraní aplikace Microsoft Office, najdete v části [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
## <a name="next-steps"></a>Další kroky  
 Informace o vytváření doplňků VSTO, najdete na následující kurzy:  
  
-   [Návod: Vytvoření vaší první Add-in VSTO pro Excel](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)  
  
-   [Návod: Vytvoření vaší první VSTO Add-In pro aplikaci Outlook](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)  
  
-   [Návod: Vytvoření vaší první Add-in VSTO pro PowerPoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)  
  
-   [Návod: Vytvoření vaší první VSTO Add-in pro projekt](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)  
  
-   [Návod: Vytvoření vaší první Add-in VSTO pro Word](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)  
  
 Tyto postupy vám představí vývojových nástrojů Office v sadě Visual Studio a programovací model pro doplňky VSTO.  
  
 Seznam témat, která vás provede procesem některé běžné úlohy v projektech Office najdete v tématu [běžné úlohy při programování pro Office](../vsto/common-tasks-in-office-programming.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Začínáme &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)  
  
  
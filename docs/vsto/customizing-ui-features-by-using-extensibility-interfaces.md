---
title: "Přizpůsobení funkcí uživatelského rozhraní pomocí rozšiřujících rozhraní | Microsoft Docs"
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
- ICustomTaskPaneConsumer interface
- IRibbonExtensibility interface
- UI customizing [Office development in Visual Studio]
- user interfaces [Office development in Visual Studio], customizing
- application-level add-ins [Office development in Visual Studio], extensibility interfaces
- customizing UI features [Office development in Visual Studio]
- FormRegionStartup interface
- add-ins [Office development in Visual Studio], extensibility interfaces
- extensibility interfaces [Office development in Visual Studio]
ms.assetid: 3f3f7908-9404-4eda-8899-4d18c75e3b4a
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 39d773ac7a4c3fa8541af30143a3d3031377b5b7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="customizing-ui-features-by-using-extensibility-interfaces"></a>Přizpůsobení funkcí uživatelského rozhraní pomocí rozšiřujících rozhraní
  Nástroje pro vývoj pro Office v sadě Visual Studio poskytují třídy a návrhářů, které zpracovávají mnoho podrobnosti implementace, když je budete používat k vytvoření vlastních podoken úloh, vlastních nastavení pásu karet a oblastí formulářů aplikace Outlook v doplňku VSTO. Ale můžete taky implementovat *rozšiřitelnost rozhraní* pro každou funkci sami, pokud máte speciální požadavky.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
## <a name="overview-of-extensibility-interfaces"></a>Přehled rozhraní rozšíření  
 Aplikace Microsoft Office definuje sadu rozhraní rozšíření, které doplňků COM VSTO můžete implementovat přizpůsobení určitých funkcí, jako je například na pásu karet. Tato rozhraní poskytují plnou kontrolu nad funkce, které poskytují přístup k. Implementace těchto rozhraní však vyžaduje některé znalost interoperabilita modelů COM ve spravovaném kódu. V některých případech programovací model tato rozhraní není také intuitivní pro vývojáře, kteří jsou uzpůsobené pro rozhraní .NET Framework.  
  
 Když vytvoříte doplňku VSTO pomocí šablony projektů Office v sadě Visual Studio, nemáte implementovat rozhraní rozšíření k přizpůsobení funkcí, jako je na pásu karet. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Implementuje tyto rozhraní za vás. Místo toho můžete intuitivnější třídy a návrhářů, poskytované sadě Visual Studio. Ale můžete pořád implementovat rozhraní rozšíření přímo v doplňku VSTO Pokud budete chtít.  
  
 Další informace o třídách a návrhářů, které Visual Studio poskytuje pro tyto funkce najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md), [Návrhář pásu karet](../vsto/ribbon-designer.md), a [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
## <a name="extensibility-interfaces-you-can-implement-in-a-vsto-add-in"></a>Rozšiřitelnost rozhraní, které můžete implementovat v doplňku VSTO  
 Následující tabulka uvádí rozhraní rozšiřitelnosti, které můžete implementovat a aplikace, které je podporují.  
  
|Rozhraní|Popis|Aplikace|  
|---------------|-----------------|------------------|  
|<xref:Microsoft.Office.Core.IRibbonExtensibility>|Implementace tohoto rozhraní pro přizpůsobení uživatelského rozhraní pásu karet. **Poznámka:** můžete přidat **pásu karet (XML)** položku do projektu pro generování výchozí <xref:Microsoft.Office.Core.IRibbonExtensibility> implementace v doplňku VSTO. Další informace najdete v tématu [XML karet](../vsto/ribbon-xml.md).|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)]<br /><br /> InfoPath 2010<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Project<br /><br /> Visio<br /><br /> Word|  
|<xref:Microsoft.Office.Core.ICustomTaskPaneConsumer>|Implementace tohoto rozhraní k vytvoření vlastního podokna úloh.|Excel<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Word|  
|<xref:Microsoft.Office.Interop.Outlook.FormRegionStartup>|Implementace tohoto rozhraní pro vytváření oblasti formuláře aplikace Outlook.|Outlook|  
  
 Existuje několik dalších rozšiřitelnost rozhraní, které jsou definovány Microsoft Office, jako například <xref:Microsoft.Office.Core.IBlogExtensibility>, <xref:Microsoft.Office.Core.EncryptionProvider>, a <xref:Microsoft.Office.Core.SignatureProvider>. Visual Studio nepodporuje implementace těchto rozhraní VSTO Add-in vytvořen pomocí šablony projektů Office.  
  
## <a name="using-extensibility-interfaces"></a>Pomocí rozšiřujících rozhraní  
 Chcete-li přizpůsobit funkce uživatelského rozhraní pomocí rozhraní rozšiřitelnosti, implementujte rozhraní odpovídající v projektu doplňku VSTO. Potom přepsat <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> metoda vrátit instanci třídy, která implementuje rozhraní.  
  
 Pro ukázkovou aplikaci, která ukazuje, jak implementovat <xref:Microsoft.Office.Core.IRibbonExtensibility>, <xref:Microsoft.Office.Core.ICustomTaskPaneConsumer>, a <xref:Microsoft.Office.Interop.Outlook.FormRegionStartup> rozhraní Add-in VSTO pro Outlook, naleznete v ukázce uživatelského rozhraní správce v [ukázky vývoje pro Office](../vsto/office-development-samples.md).  
  
### <a name="example-of-implementing-an-extensibility-interface"></a>Příklad implementace rozhraní rozšíření  
 Následující příklad kódu ukazuje jednoduchou implementaci <xref:Microsoft.Office.Core.ICustomTaskPaneConsumer> rozhraní pro vytváření vlastního podokna úloh. Tento příklad definuje dvě třídy:  
  
-   `TaskPaneHelper` Třída implementuje <xref:Microsoft.Office.Core.ICustomTaskPaneConsumer> k vytváření a zobrazování vlastního podokna úloh.  
  
-   `TaskPaneUI` Třída poskytuje uživatelské rozhraní v podokně úloh. Atributy `TaskPaneUI` třída zviditelnit třídu do modelu COM, umožňující aplikace Microsoft Office ke zjištění třídy. V tomto příkladu je rozhraní prázdnou <xref:System.Windows.Forms.UserControl>, ale můžete přidat ovládací prvky změny kódu.  
  
    > [!NOTE]  
    >  Ke zveřejnění `TaskPaneUI` třída do modelu COM, musíte taky nastavit **zaregistrovat zprostředkovatel komunikace s objekty COM** vlastnosti projektu.  
  
 [!code-vb[Trin_SimpleExtensibilityInterface#1](../vsto/codesnippet/VisualBasic/Trin_SimpleExtensibilityInterface/ThisAddIn.vb#1)]
 [!code-csharp[Trin_SimpleExtensibilityInterface#1](../vsto/codesnippet/CSharp/Trin_SimpleExtensibilityInterface/ThisAddIn.cs#1)]  
  
 Další informace o implementaci <xref:Microsoft.Office.Core.ICustomTaskPaneConsumer>, najdete v části [vytváření podokna úloh Vlastní v systému Office 2007](http://msdn.microsoft.com/en-us/256313db-18cc-496c-a961-381ed9ca94be) v dokumentaci k Microsoft Office.  
  
### <a name="example-of-overriding-the-requestservice-method"></a>Příklad přepsání metody RequestService  
 Následující příklad kódu ukazuje, jak lze přepsat <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> metoda vrátí instanci `TaskPaneHelper` třídy z předchozího příkladu kódu. Zkontroluje hodnotu *serviceGuid* parametr k určení, které rozhraní je požadováno a vrátí objekt, který implementuje rozhraní.  
  
 [!code-vb[Trin_SimpleExtensibilityInterface#2](../vsto/codesnippet/VisualBasic/Trin_SimpleExtensibilityInterface/ThisAddIn.vb#2)]
 [!code-csharp[Trin_SimpleExtensibilityInterface#2](../vsto/codesnippet/CSharp/Trin_SimpleExtensibilityInterface/ThisAddIn.cs#2)]  
  
## <a name="see-also"></a>Viz také  
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)  
  
  
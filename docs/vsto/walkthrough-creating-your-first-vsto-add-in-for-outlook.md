---
title: "Návod: Vytvoření vašeho prvního doplňku VSTO pro Outlook | Microsoft Docs"
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
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- add-ins [Office development in Visual Studio], creating your first project
- Outlook [Office development in Visual Studio], creating your first project
ms.assetid: 2c5c5d75-27ee-471f-9328-58f0cf05b2b7
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: a5fb633d58485ab605cbfed1d3bddeb7b70e100f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-your-first-vsto-add-in-for-outlook"></a>Postup: Vytvoření prvního doplňku VSTO pro Outlook
  Tento návod ukazuje, jak vytvořit doplňku VSTO pro aplikaci Microsoft Office Outlook. Funkce, které vytvoříte v tento druh řešení jsou k dispozici pro aplikace, samostatně, bez ohledu na to, který je otevřete položku aplikace Outlook. Další informace najdete v tématu [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření projektu doplňku VSTO pro Outlook pro aplikaci Outlook.  
  
-   Psaní kódu, který používá objektový model aplikace Outlook k přidání textu do předmět a text novou e-mailovou zprávu.  
  
-   Sestavení a spuštění projektu to vyzkoušíte.  
  
-   Čistí dokončený projekt tak, aby doplňku VSTO již nebude automaticky spustí na svém vývojovém počítači.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Outlook  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
  
#### <a name="to-create-a-new-outlook-project-in-visual-studio"></a>Chcete-li vytvořit nový projekt aplikace Outlook v sadě Visual Studio  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.  
  
4.  V části sada rozšířeného **Office/SharePoint** uzlu, vyberte **Office Add in** uzlu.  
  
5.  V seznamu šablon projektu zvolte projektu doplňku VSTO v Outlooku.  
  
6.  V **název** zadejte **FirstOutlookAddIn**.  
  
7.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]vytvoří **FirstOutlookAddIn** projektu a otevře **ThisAddIn** souboru kódu v editoru.  
  
## <a name="writing-code-that-adds-text-to-each-new-mail-message"></a>Psaní kódu, který přidává Text pro každou novou e-mailovou zprávu  
 Dál přidejte kód do souboru kódu ThisAddIn. Nový kód používá objektový model aplikace Outlook k přidání textu do každé nové e-mailovou zprávu. Ve výchozím nastavení soubor ThisAddIn kód obsahuje následující generovaný kód:  
  
-   Částečné definice `ThisAddIn` třídy. Tato třída představuje vstupní bod pro kód a poskytuje přístup k modelu objektů aplikace Outlook. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md). Zbývající část `ThisAddIn` třída definovaná v souboru skrytá kódu, který byste neměli upravovat.  
  
-   `ThisAddIn_Startup` a `ThisAddIn_Shutdown` obslužné rutiny událostí. Tyto obslužné rutiny událostí jsou volány při Outlook načte a uvolní vaší doplňku VSTO. Pomocí těchto obslužných rutin událostí k chybě při inicializaci doplňku VSTO, když je načten a vyčistit prostředky využívané třídou vaší doplňku VSTO v případě, že je odpojen. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
#### <a name="to-add-text-to-the-subject-and-body-of-each-new-mail-message"></a>Chcete-li přidat text pro předmět a text každého nového e-mailovou zprávu  
  
1.  V souboru kódu ThisAddIn deklarovat pole s názvem `inspectors` v `ThisAddIn` třídy. `inspectors` Pole udržuje odkaz na kolekci systému windows, nástroj Inspector v aktuální instanci aplikace Outlook. Tento odkaz brání uvolnění paměti, která obsahuje obslužné rutiny události pro uvolňování paměti <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> událostí.  
  
     [!code-vb[Trin_OutlookAddInTutorial#1](../vsto/codesnippet/VisualBasic/Trin_OutlookAddInTutorial/ThisAddIn.vb#1)]
     [!code-csharp[Trin_OutlookAddInTutorial#1](../vsto/codesnippet/CSharp/Trin_OutlookAddInTutorial/ThisAddIn.cs#1)]  
  
2.  Nahraďte `ThisAddIn_Startup` metoda následujícím kódem. Připojí obslužné rutiny události pro tento kód <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> událostí.  
  
     [!code-vb[Trin_OutlookAddInTutorial#2](../vsto/codesnippet/VisualBasic/Trin_OutlookAddInTutorial/ThisAddIn.vb#2)]
     [!code-csharp[Trin_OutlookAddInTutorial#2](../vsto/codesnippet/CSharp/Trin_OutlookAddInTutorial/ThisAddIn.cs#2)]  
  
3.  V souboru kódu ThisAddIn, přidejte následující kód, který `ThisAddIn` třídy. Tento kód definuje obslužnou rutinu události pro <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> událostí.  
  
     Když uživatel vytvoří novou e-mailovou zprávu, přidá této obslužné rutiny události text předmět a text zprávy.  
  
     [!code-vb[Trin_OutlookAddInTutorial#3](../vsto/codesnippet/VisualBasic/Trin_OutlookAddInTutorial/ThisAddIn.vb#3)]
     [!code-csharp[Trin_OutlookAddInTutorial#3](../vsto/codesnippet/CSharp/Trin_OutlookAddInTutorial/ThisAddIn.cs#3)]  
  
 Chcete-li upravit každou novou e-mailovou zprávu, použijte předchozí příklady kódu následující objekty:  
  
-   `Application` Pole z `ThisAddIn` třídy. `Application` Pole vrátí <xref:Microsoft.Office.Interop.Outlook.Application> objektu, který představuje aktuální instanci aplikace Outlook.  
  
-   `Inspector` Parametr obslužné rutiny události pro <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> událostí. `Inspector` Parametr <xref:Microsoft.Office.Interop.Outlook.Inspector> objekt, který reprezentuje okno Inspector novou e-mailovou zprávu. Další informace najdete v tématu [řešení pro aplikaci Outlook](../vsto/outlook-solutions.md).  
  
## <a name="testing-the-project"></a>Testování projektu  
 Při sestavení a spuštění projektu, ověřte, že text se zobrazí v předmět a text novou e-mailovou zprávu.  
  
#### <a name="to-test-the-project"></a>Otestování projektu  
  
1.  Stiskněte klávesu **F5** sestavení a spuštění projektu.  
  
     Při sestavování projektu se zkompilovat kód do sestavení, které je součástí složku výstupu sestavení pro projekt. Visual Studio také vytvoří sadu položky registru, které umožňují Outlook zjišťovat a načíst doplňku VSTO a nakonfiguruje nastavení zabezpečení na vývojovém počítači povolit doplňku VSTO ke spuštění. Další informace najdete v tématu [přehled procesu sestavení řešení Office](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md).  
  
2.  V aplikaci Outlook vytvořte novou e-mailovou zprávu.  
  
3.  Ověřte, zda je přidána následující text k předmět a text zprávy.  
  
     **Tento text byl přidán pomocí kódu.**  
  
4.  Zavřete aplikaci Outlook.  
  
## <a name="cleaning-up-the-project"></a>Čištění projektu  
 Po dokončení vývoj projektu, odeberte z vývojovém počítači doplňku VSTO sestavení, položky registru a nastavení zabezpečení. V opačném doplňku VSTO se spustí pokaždé, když otevřete aplikaci Outlook na vývojovém počítači.  
  
#### <a name="to-clean-up-your-project"></a>Vyčistěte projekt  
  
1.  V sadě Visual Studio na **sestavení** nabídky, klikněte na tlačítko **Vyčistit řešení**.  
  
## <a name="next-steps"></a>Další kroky  
 Teď, když jste vytvořili základní VSTO Add-in pro aplikaci Outlook, další informace o tom, jak vyvíjet doplňků VSTO z těchto témat:  
  
-   Obecné programování úlohy, které můžete provádět pomocí doplňků VSTO pro Outlook. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
-   Pomocí modelu objektů aplikace Outlook. Další informace najdete v tématu [řešení pro aplikaci Outlook](../vsto/outlook-solutions.md).  
  
-   Přizpůsobení uživatelského rozhraní Outlook například vytvoření vlastní karty na pásu karet nebo vytvořit vlastní vlastního podokna úloh. Další informace najdete v tématu [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
-   Sestavování a ladění doplňků VSTO pro Outlook. Další informace najdete v tématu [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
-   Nasazení doplňků VSTO pro Outlook. Další informace najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také  
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Řešení pro aplikaci Outlook](../vsto/outlook-solutions.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Přehled šablon projektů Microsoft Office Project](../vsto/office-project-templates-overview.md)  
  
  
---
title: "Návod: Vytvoření vašeho prvního doplňku VSTO pro projekt | Microsoft Docs"
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
- Project [Office development in Visual Studio], creating your first project
- add-ins [Office development in Visual Studio], creating your first project
ms.assetid: da2b727e-6db8-4853-bf00-7afe0ef13213
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 391bd4bbdfe87f1bc00ac14356c61f988b8bf041
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-your-first-vsto-add-in-for-project"></a>Návod: Vytvoření vašeho prvního doplňku VSTO pro projekt
  Tento návod ukazuje, jak vytvořit doplňku VSTO pro aplikaci Microsoft Office Project. Funkce, které vytvoříte v tento druh řešení jsou k dispozici pro aplikace, samostatně, bez ohledu na to, které jsou otevřené projekty. Další informace najdete v tématu [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_projallapp](../vsto/includes/appliesto-projallapp-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření projektu doplňku VSTO projektu.  
  
-   Psaní kódu, který používá objektový model projektu přidat úloha do nového projektu.  
  
-   Sestavení a spuštění projektu to vyzkoušíte.  
  
-   Čistí dokončený projekt tak, aby doplňku VSTO již nebude automaticky spustí na svém vývojovém počítači.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Project_15_short](../vsto/includes/project-15-short-md.md)]nebo [!INCLUDE[Project_14_short](../vsto/includes/project-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
  
#### <a name="to-create-a-new-project-in-visual-studio"></a>Chcete-li vytvořit nový projekt v sadě Visual Studio  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.  
  
4.  V části sada rozšířeného **Office/SharePoint** uzlu, vyberte **Office Add in** uzlu.  
  
5.  V seznamu šablon projektu, vyberte **doplněk 2010 projektu** nebo **Add-in 2013 projektu**.  
  
6.  V **název** zadejte **FirstProjectAddIn**.  
  
7.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]vytvoří **FirstProjectAddIn** projektu a otevře **ThisAddIn** souboru kódu v editoru.  
  
## <a name="writing-code-that-adds-a-new-task-to-a-project"></a>Psaní kódu, který přidá novou úlohu do projektu  
 Dál přidejte kód do souboru kódu ThisAddIn. Nový kód používá objektový model projektu k přidání nové úlohy do projektu. Ve výchozím nastavení soubor ThisAddIn kód obsahuje následující generovaný kód:  
  
-   Částečné definice `ThisAddIn` třídy. Tato třída představuje vstupní bod pro kód a poskytuje přístup k modelu objektu projektu. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md). Zbývající část `ThisAddIn` třída definovaná v souboru skrytá kódu, který byste neměli upravovat.  
  
-   `ThisAddIn_Startup` a `ThisAddIn_Shutdown` obslužné rutiny událostí. Tyto obslužné rutiny událostí jsou volány při projektu načte a uvolní vaší doplňku VSTO. Pomocí těchto obslužných rutin událostí k chybě při inicializaci doplňku VSTO, když je načten a vyčistit prostředky využívané třídou vaší doplňku VSTO v případě, že je odpojen. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
#### <a name="to-add-a-task-to-a-new-project"></a>Chcete-li přidat úloha na nový projekt  
  
1.  V souboru kódu ThisAddIn, přidejte následující kód, který `ThisAddIn` třídy. Tento kód definuje obslužnou rutinu události pro událost NewProject Microsoft.Office.Interop.MSProject.Application třídy.  
  
     Když uživatel vytvoří nový projekt, přidá této obslužné rutiny události úlohu do projektu.  
  
     [!code-vb[Trin_ProjectAddInTutorial#1](../vsto/codesnippet/VisualBasic/Trin_ProjectAddInTutorial/ThisAddIn.vb#1)]
     [!code-csharp[Trin_ProjectAddInTutorial#1](../vsto/codesnippet/CSharp/Trin_ProjectAddInTutorial/ThisAddIn.cs#1)]  
  
 Chcete-li upravit projektu, použijte tento příklad kódu následující objekty:  
  
-   `Application` Pole z `ThisAddIn` třídy. `Application` Pole vrátí objekt Microsoft.Office.Interop.MSProject.Application, který představuje aktuální instanci projektu.  
  
-   `pj` Parametr obslužné rutiny události pro událost NewProject. `pj` Parametr je Microsoft.Office.Interop.MSProject.Project objekt, který reprezentuje projektu. Další informace najdete v tématu [řešení projektu](../vsto/project-solutions.md).  
  
1.  Pokud používáte C#, přidejte následující kód, který `ThisAddIn_Startup` obslužné rutiny události. Tento kód se připojí `Application_Newproject` obslužné rutiny události s NewProject událostí.  
  
     [!code-csharp[Trin_ProjectAddInTutorial#2](../vsto/codesnippet/CSharp/Trin_ProjectAddInTutorial/ThisAddIn.cs#2)]  
  
-  
  
## <a name="testing-the-project"></a>Testování projektu  
 Při sestavení a spuštění projektu, ověřte, že nová úloha se zobrazí v výsledné nový projekt.  
  
#### <a name="to-test-the-project"></a>Otestování projektu  
  
1.  Stiskněte klávesu **F5** sestavení a spuštění projektu. Aplikace Microsoft Project spustí a automaticky se otevře nový prázdný projekt.  
  
     Při sestavování projektu se zkompilovat kód do sestavení, které je součástí složku výstupu sestavení pro projekt. Visual Studio také vytvoří sadu položky registru, které umožňují projektu zjišťovat a načíst doplňku VSTO a nakonfiguruje nastavení zabezpečení na vývojovém počítači povolit doplňku VSTO ke spuštění. Další informace najdete v tématu [přehled procesu sestavení řešení Office](http://msdn.microsoft.com/en-us/a9d12e4f-c9ea-4a62-a841-c42b91f831ee).  
  
2.  Zkontrolujte, zda je na prázdný projekt přidána nové úlohy.  
  
3.  Ověřte, že tento text se zobrazí v **název úlohy** pole úlohy.  
  
     **Tento text byl přidán pomocí kódu.**  
  
4.  Zavřete Microsoft Project.  
  
## <a name="cleaning-up-the-project"></a>Čištění projektu  
 Po dokončení vývoj projektu, odeberte z vývojovém počítači doplňku VSTO sestavení, položky registru a nastavení zabezpečení. V opačném doplňku VSTO se spustí při každém otevření Microsoft Project na vývojovém počítači.  
  
#### <a name="to-clean-up-your-project"></a>Vyčistěte projekt  
  
1.  V sadě Visual Studio na **sestavení** nabídky, klikněte na tlačítko **Vyčistit řešení**.  
  
## <a name="next-steps"></a>Další kroky  
 Teď, když jste vytvořili základní VSTO Add-in pro projekt, další informace o tom, jak vyvíjet doplňků VSTO z těchto témat:  
  
-   Obecné programování úlohy, které můžete provádět v doplňků VSTO pro projekt: [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
-   Pomocí objektu modelu projektu: [řešení projektu](../vsto/project-solutions.md).  
  
-   Sestavování a ladění doplňků VSTO pro projekt: [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
-   Nasazení doplňků VSTO pro projekt: [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také  
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Projektová řešení](../vsto/project-solutions.md)   
 [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Přehled šablon projektů Microsoft Office Project](../vsto/office-project-templates-overview.md)  
  
  
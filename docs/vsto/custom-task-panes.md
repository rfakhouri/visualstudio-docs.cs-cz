---
title: "Vlastní podokna úloh | Microsoft Docs"
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
- Office development in Visual Studio, task panes
- user interface panels [Office development in Visual Studio]
- task panes [Office development in Visual Studio]
- user interfaces [Office development in Visual Studio], custom task panes
- custom task panes [Office development in Visual Studio], creating
- task panes [Office development in Visual Studio]. multiple application windows
- custom task panes [Office development in Visual Studio], multiple application windows
- task panes [Office development in Visual Studio], creating
- application-level add-ins [Office development in Visual Studio], custom task panes
- multiple applications windows with custom task panes [Office development in Visual Studio]
- add-ins [Office development in Visual Studio], custom task panes
- custom task panes [Office development in Visual Studio]
- task panes [Office development in Visual Studio], about custom task panes
- custom task panes [Office development in Visual Studio], about custom task panes
ms.assetid: 9a415109-5333-433e-95c6-3d59ce9c4d02
caps.latest.revision: "52"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 097a4247ccc7604dd4c39b81e0f733578fc91c89
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="custom-task-panes"></a>Vlastní podokna úloh
  Podokna úloh jsou panely uživatelského rozhraní, které jsou obvykle ukotven na jedné straně okna v aplikaci Microsoft Office. Vlastní podokna úloh poskytují způsob, jak vytvořit vlastní podokna úloh a uživatelům poskytnout známé rozhraní pro přístup k funkcím vaše řešení. Rozhraní může například obsahovat ovládacích prvků, které kód upravovat dokumenty nebo zobrazovat data ze zdroje dat spustit.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  V podokně Akce se liší vlastního podokna úloh. V podokně Akce je součástí úpravy na úrovni dokumentů pro Microsoft Office Word a Microsoft Office Excel. Další informace najdete v tématu [přehled podokna akcí](../vsto/actions-pane-overview.md).  
  
## <a name="benefits-of-custom-task-panes"></a>Výhody vlastní podokna úloh  
 Vlastní podokna úloh umožňují integrovat váš funkce do známé uživatelské rozhraní. Vlastního podokna úloh můžete rychle vytvořit pomocí nástrojů Visual Studio.  
  
### <a name="familiar-user-interface"></a>Známé uživatelské rozhraní  
 Uživatelé aplikací v systému Microsoft Office obeznámeni s pomocí podokna úloh, jako **styly a formátování** podokna úloh v aplikaci Word. Vlastní podokna úloh chovat jako další podokna úloh v systému Microsoft Office. Uživatele můžete ukotvit vlastních podoken úloh různých stranách okna aplikace, nebo se můžete přetáhnout vlastní podokna úloh do libovolného umístění, v okně. Můžete vytvořit Add-in VSTO, která zobrazuje více vlastních podoken úloh ve stejnou dobu, a uživatelé můžou řídit jednotlivě každý podokna úloh.  
  
### <a name="windows-forms-support"></a>Podpora prostředí Windows Forms  
 Uživatelské rozhraní z vlastního podokna úloh, které vytvoříte pomocí nástrojů pro vývoj pro Office v sadě Visual Studio je založena na systému Windows Forms – ovládací prvky. Známé Návrhář formulářů Windows můžete použít k návrhu uživatelského rozhraní pro vlastního podokna úloh. Můžete taky podporu vazby dat v systému Windows Forms svázat zdroj dat s ovládacími prvky v podokně úloh.  
  
## <a name="creating-a-custom-task-pane"></a>Vytvoření vlastního podokna úloh  
 Můžete vytvořit základní vlastního podokna úloh ve dvou krocích:  
  
1.  Přidání ovládacích prvků Windows Forms k vytvořit uživatelské rozhraní pro vlastního podokna úloh <xref:System.Windows.Forms.UserControl> objektu.  
  
2.  Vytvořte instanci vlastního podokna úloh předáním uživatelského ovládacího prvku <xref:Microsoft.Office.Tools.CustomTaskPaneCollection> objekt v doplňku VSTO. Tato kolekce vrátí novou <xref:Microsoft.Office.Tools.CustomTaskPane> objekt, který můžete použít k úpravě vzhled do podokna úloh a reakce na události uživatele.  
  
 Další informace najdete v tématu [postupy: Přidání vlastního podokna úloh do aplikace](../vsto/how-to-add-a-custom-task-pane-to-an-application.md).  
  
### <a name="creating-the-user-interface"></a>Vytvoření uživatelského rozhraní  
 Obsahuje všechny vlastní podokna úloh vytvořených pomocí nástroje pro vývoj pro Office v sadě Visual Studio <xref:System.Windows.Forms.UserControl> objektu. Tento uživatelský ovládací prvek poskytuje uživatelské rozhraní z vlastního podokna úloh. Můžete vytvořit uživatelského ovládacího prvku v době návrhu nebo za běhu. Pokud vytvoříte uživatelského ovládacího prvku v době návrhu, můžete vytvořit uživatelské rozhraní podokna úloh Návrhář formulářů Windows.  
  
### <a name="instantiating-the-custom-task-pane"></a>Vytváření instancí vlastního podokna úloh  
 Po vytvoření uživatelského ovládacího prvku, který obsahuje uživatelské rozhraní z vlastního podokna úloh, budete muset vytvořit instanci <xref:Microsoft.Office.Tools.CustomTaskPane>. K tomuto účelu předat uživatelského ovládacího prvku <xref:Microsoft.Office.Tools.CustomTaskPaneCollection> v doplňku VSTO ve volání jedné z <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> metody. Tato kolekce je zpřístupněná jako `CustomTaskPanes` pole z `ThisAddIn` třídy. Následující příklad kódu je určený pro spouštění z `ThisAddIn` třídy.  
  
 [!code-vb[Trin_TaskPaneBasic#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#2)]
 [!code-csharp[Trin_TaskPaneBasic#2](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#2)]  
  
 <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> Metody vracet novou <xref:Microsoft.Office.Tools.CustomTaskPane> objektu. Tento objekt můžete použít k úpravě vzhled do podokna úloh a reakce na události uživatele.  
  
### <a name="controlling-the-task-pane-in-multiple-windows"></a>Řízení v podokně úloh ve více oken  
 Vlastní podokna úloh jsou přidruženy k rámce okna dokumentu, který se uživateli zobrazí zobrazení dokumentu nebo položce. V podokně úloh je viditelná jenom v případě, že okno přidružené je viditelné.  
  
 Pokud chcete zjistit, které zobrazují vlastního podokna úloh, použijte odpovídající <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> přetížení metody vytvoříte-li do podokna úloh:  
  
-   Chcete-li do podokna úloh přidružit k aktivní okno, použijte <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> metoda.  
  
-   Chcete-li do podokna úloh přidružit dokument, který je hostován vybrané okno, použijte <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> metoda.  
  
 Některé aplikace Office vyžadují explicitní pokyny, kdy se mají vytvořit nebo zobrazit vaše podokna úloh, pokud je otevřené okno více než jeden. Díky tomu je potřeba zvážit, kde se vytvořit instanci vlastního podokna úloh ve vašem kódu, chcete-li zajistit, aby se do podokna úloh s příslušnou dokumenty či položky v aplikaci. Další informace najdete v tématu [Správa podokna vlastní úloh v aplikaci Windows](#Managing).  
  
## <a name="accessing-the-application-from-the-task-pane"></a>Přístup k aplikaci v podokně úloh  
 Pokud chcete automatizovat aplikace z uživatelského ovládacího prvku, můžete přímo přístup k objektu modelu s použitím `Globals.ThisAddIn.Application` ve vašem kódu. Statické `Globals` třída poskytuje přístup k `ThisAddIn` objektu. `Application` Pole tohoto objektu je vstupní bod do modelu objektu aplikace.  
  
 Další informace o `Application` pole z `ThisAddIn` objektu, najdete v části [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md). Návod, jak to automatizace aplikace z vlastního podokna úloh najdete v tématu [návod: automatizace aplikace z vlastního podokna úloh](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md). Další informace o `Globals` třídy najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
## <a name="managing-the-user-interface-of-the-task-pane"></a>Správa uživatelského rozhraní do podokna úloh  
 Po vytvoření do podokna úloh, můžete použít vlastnosti a události <xref:Microsoft.Office.Tools.CustomTaskPane> objekt k ovládání uživatelského rozhraní v podokně úloh a reagovat, když uživatel změní v podokně úloh.  
  
### <a name="making-the-custom-task-pane-visible"></a>Viditelnosti vlastního podokna úloh  
 Ve výchozím nastavení v podokně úloh není viditelný. Chcete-li do podokna úloh zobrazené, musíte nastavit <xref:Microsoft.Office.Tools.CustomTaskPane.Visible%2A> vlastnost **true**.  
  
 Uživatele můžete kdykoli zavřít podokna úloh, kliknutím **zavřete** tlačítko (X) v dolním podokně úloh. Je však žádné výchozí uživatelům způsob, jak otevřít vlastního podokna úloh znovu. Pokud uživatel zavře vlastního podokna úloh, tohoto uživatele nelze zobrazit vlastního podokna úloh znovu Pokud poskytnout způsob, můžete ho zobrazit.  
  
 Pokud vytvoříte vlastního podokna úloh v doplňku VSTO, měli byste také vytvořit element uživatelského rozhraní, jako je tlačítko, které mohou uživatelé kliknout a zobrazit nebo skrýt vlastního podokna úloh. Pokud vytvoříte vlastního podokna úloh v aplikaci Microsoft Office, který podporuje přizpůsobení pásu karet, můžete přidat skupinu ovládacích prvků na pásu karet pomocí tlačítka, který zobrazí nebo skryje vlastního podokna úloh. Návod, jak to udělat najdete v tématu [návod: synchronizace vlastního podokna úloh s tlačítkem pásu karet](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md).  
  
 Pokud vytvoříte vlastního podokna úloh v aplikaci Microsoft Office, která nepodporuje přizpůsobení pásu karet, můžete přidat <xref:Microsoft.Office.Core.CommandBarButton> , zobrazí nebo skryje vlastního podokna úloh.  
  
### <a name="modifying-the-appearance-of-the-task-pane"></a>Změna vzhledu ovládacího do podokna úloh  
 Velikost a umístění vlastního podokna úloh můžete řídit pomocí vlastnosti <xref:Microsoft.Office.Tools.CustomTaskPane> objektu. Můžete provádět mnoho dalších změn vzhled vlastního podokna úloh pomocí vlastnosti <xref:System.Windows.Forms.UserControl> objekt, který je součástí vlastního podokna úloh. Například můžete zadat obrázek pozadí pro vlastního podokna úloh s použitím <xref:System.Windows.Forms.Control.BackgroundImage%2A> vlastnost uživatelského ovládacího prvku.  
  
 Následující tabulka obsahuje seznam změn, můžete provést pomocí vlastního podokna úloh <xref:Microsoft.Office.Tools.CustomTaskPane> vlastnosti.  
  
|Úloha|Vlastnost|  
|----------|--------------|  
|Chcete-li změnit velikost podokna úloh|<xref:Microsoft.Office.Tools.CustomTaskPane.Height%2A><br /><br /> <xref:Microsoft.Office.Tools.CustomTaskPane.Width%2A>|  
|Chcete-li změnit umístění do podokna úloh|<xref:Microsoft.Office.Tools.CustomTaskPane.DockPosition%2A>|  
|Skrytí podokna úloh nebo zviditelnit|<xref:Microsoft.Office.Tools.CustomTaskPane.Visible%2A>|  
|Chcete-li uživateli zabránit ve změně umístění do podokna úloh|<xref:Microsoft.Office.Tools.CustomTaskPane.DockPositionRestrict%2A>|  
  
### <a name="programming-custom-task-pane-events"></a>Programování událostí podokně vlastní úlohy  
 Můžete chtít doplňku VSTO reagovat, když uživatel změní vlastního podokna úloh. Například pokud uživatel změní na vodorovné orientaci v podokně ze svislé, můžete chtít změnit umístění ovládacích prvků.  
  
 Následující tabulka uvádí události, které může zpracovat reagovat na změny, které uživatel provede vlastního podokna úloh.  
  
|Úloha|Událost|  
|----------|-----------|  
|Reagovat, když uživatel změní umístění do podokna úloh.|<xref:Microsoft.Office.Tools.CustomTaskPane.DockPositionChanged>|  
|Reagovat, když uživatel do podokna úloh skryje nebo zobrazí ho.|<xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged>|  
  
## <a name="cleaning-up-resources-used-by-the-task-pane"></a>Vymazání prostředků používané do podokna úloh  
 Po vytvoření vlastního podokna úloh, <xref:Microsoft.Office.Tools.CustomTaskPane> objekt zůstávají v paměti, dokud je spuštěna vaše doplňku VSTO. Objekt zůstane v paměti i poté, co uživatel klikne **Zavřít** tlačítko (X) v dolním podokně úloh.  
  
 Chcete-li vyčistit prostředky používané v podokně úloh doplňku VSTO stále běží, použijte <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Remove%2A> nebo <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.RemoveAt%2A> metody. Tyto metody odeberte zadaný <xref:Microsoft.Office.Tools.CustomTaskPane> objektu z `CustomTaskPanes` kolekce a volání <xref:Microsoft.Office.Tools.CustomTaskPane.Dispose%2A> metodu objektu.  
  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Automaticky vyčistí prostředky využívané třídou vlastního podokna úloh po doplňku VSTO odpojen. Nevolejte <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Remove%2A> nebo <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.RemoveAt%2A> metody v `ThisAddIn_Shutdown` obslužné rutiny události ve vašem projektu. Tyto metody vyvolá výjimku <xref:System.ObjectDisposedException>, protože [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] vyčistí prostředky používané <xref:Microsoft.Office.Tools.CustomTaskPane> objekt před `ThisAddIn_Shutdown` je volána. Další informace o `ThisAddIn_Shutdown`, najdete v části [události v projektech pro systém Office](../vsto/events-in-office-projects.md)  
  
##  <a name="Managing"></a>Správa vlastních podoken úloh v více oken aplikace  
 Když vytvoříte vlastního podokna úloh v aplikaci, která používá více oken pro zobrazení dokumentů a dalších položkách, budete muset provést další kroky k zajištění, že v podokně úloh je zobrazena, pokud uživatel očekává, že se.  
  
 Vlastní podokna úloh ve všech aplikací jsou přidruženy k rámce okna dokumentu, který se uživateli zobrazí zobrazení dokumentu nebo položce. V podokně úloh je viditelná jenom v případě, že okno přidružené je viditelné. Ale ne všechny aplikace pomocí okna s rámečkem v dokumentu stejným způsobem.  
  
 Tyto skupiny aplikací mít vývoj pro různé požadavky:  
  
-   [Aplikace Outlook](#Outlook)  
  
-   [Word, PowerPoint a InfoPath](#WordAndInfoPath)  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: Spravovat podokna úloh v doplňků VSTO pro Word?](http://go.microsoft.com/fwlink/?LinkId=136781).  
  
##  <a name="Outlook"></a>Aplikace Outlook  
 Když vytvoříte vlastního podokna úloh pro aplikaci Outlook, je přidružen konkrétní okno Průzkumníka nebo Inspector vlastního podokna úloh. Průzkumníci jsou windows, které zobrazovat obsah složky a kontroly systému windows, které zobrazí položky jako e-mailové zprávě nebo úlohu.  
  
 Pokud chcete zobrazit vlastního podokna úloh s více nástroj Inspector nebo Průzkumníka windows, budete muset vytvořit novou instanci vlastního podokna úloh, když se otevře okno s Průzkumníka nebo Inspector. K tomu zpracovat událost, která se vyvolá, když se vytvoří okno s Průzkumníka nebo Inspector a vytvořte v podokně úloh v obslužné rutině. Můžete také zpracovat události Průzkumníka a Inspector ke skrytí nebo zobrazení podokna úloh v závislosti na tom, které okno se zobrazí.  
  
 Chcete-li do podokna úloh přidružit určité Explorer nebo Inspector, použijte <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> metodu pro vytvoření do podokna úloh a předat <xref:Microsoft.Office.Interop.Outlook.Explorer> nebo <xref:Microsoft.Office.Interop.Outlook.Inspector> do objektu *okno* parametr. Další informace o vytváření vlastních podoken úloh najdete v tématu [vlastní přehled podokna úloh](../vsto/custom-task-panes.md).  
  
 Návod, který ukazuje, jak vytvořit podokna úloh pro každou e-mailová zpráva, která je otevřená, najdete v části [návod: zobrazení vlastních podoken s e-mailových zpráv v aplikaci Outlook](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md).  
  
### <a name="outlook-events"></a>Události aplikace Outlook  
 Chcete-li monitorovat stav Průzkumníka windows, může zpracovávat následující události související s Explorer:  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorersEvents_Event.NewExplorer>  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Activate>  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Close>  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Deactivate>  
  
 Chcete-li monitorovat stav Inspector windows, může zpracovávat následující události související s Inspector:  
  
-   <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector>  
  
-   <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_10_Event.Activate>  
  
-   <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_10_Event.Close>  
  
-   <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_10_Event.Deactivate>  
  
### <a name="preventing-multiple-instances-of-a-custom-task-pane-in-outlook"></a>Brání více instancí vlastního podokna úloh v aplikaci Outlook  
 Chcete-li zabránit zobrazování více instancí vlastního podokna úloh Outlook windows, explicitně odeberte vlastního podokna úloh z `CustomTaskPanes` kolekce `ThisAddIn` třídy při zavření každý okna. Volání <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Remove%2A> metoda v událost, která se vyvolá při zavření okna, jako například <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Close> nebo <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_10_Event.Close>.  
  
 Pokud vlastního podokna úloh není explicitně odebrat, Outlook windows se může zobrazit více instancí vlastního podokna úloh. Outlook někdy recykluje windows a windows recykluje zachovat odkazy na všechny vlastní podokna úloh, která byla připojena k nim.  
  
##  <a name="WordAndInfoPath"></a>Word, PowerPoint a InfoPath  
 Word, PowerPoint a InfoPath zobrazí v okně s rámečkem jiného dokumentu každého dokumentu. Když vytvoříte vlastního podokna úloh pro tyto aplikace, je přidruženo pouze konkrétní dokumentu vlastního podokna úloh. Pokud uživatel otevře do jiného dokumentu, vlastního podokna úloh je skryté, dokud starší dokumentu se znovu nezobrazí.  
  
 Pokud chcete zobrazit vlastního podokna úloh s více dokumenty, vytvořte novou instanci třídy vlastního podokna úloh, když uživatel vytvoří nový dokument nebo otevře existující dokument. K tomuto účelu zpracování událostí, které se vyvolá, když je vytvořit nebo otevřít dokument a pak ve obslužné rutiny událostí vytvořit v podokně úloh. Můžete také zpracovat události dokumentu ke skrytí nebo zobrazení podokna úloh v závislosti na tom, který dokument je viditelná.  
  
 Chcete-li do podokna úloh přidružit okna konkrétní dokumentu, použijte <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> metodu pro vytvoření do podokna úloh a předat <xref:Microsoft.Office.Interop.Word.Window> (pro Word), <xref:Microsoft.Office.Interop.InfoPath.WindowObject> (pro aplikaci InfoPath), nebo <xref:Microsoft.Office.Interop.PowerPoint.DocumentWindow> (pro PowerPoint) k *okno*parametr.  
  
### <a name="word-events"></a>Události aplikace Word  
 Chcete-li sledovat stav windows dokumentu ve Wordu, může zpracovávat následující události:  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeClose>  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen>  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.NewDocument>  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.WindowActivate>  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.WindowDeactivate>  
  
### <a name="infopath-events"></a>InfoPath události  
 Chcete-li sledovat stav okna dokumentu v aplikaci InfoPath, může zpracovávat následující události:  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.NewXDocument>  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowActivate>  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowDeactivate>  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeClose>  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentOpen>  
  
### <a name="powerpoint-events"></a>PowerPoint události  
 Chcete-li sledovat stav okna dokumentu v PowerPointu, může zpracovávat následující události:  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.AfterNewPresentation>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.AfterPresentationOpen>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.NewPresentation>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.PresentationOpen>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.WindowActivate>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.WindowDeactivate>  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Přidání vlastního podokna úloh do aplikace](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [Návod: Automatizace aplikace z vlastního podokna úloh](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)   
 [Návod: Synchronizace vlastního podokna úloh s tlačítkem pásu karet](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md)   
 [Návod: Zobrazení vlastních podoken úloh s e-mailových zpráv v aplikaci Outlook](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md)  

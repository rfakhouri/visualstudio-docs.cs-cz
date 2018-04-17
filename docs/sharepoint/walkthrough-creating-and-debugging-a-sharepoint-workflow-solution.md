---
title: 'Návod: Vytváření a ladění řešení pracovního postupu služby SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Workflow.WorkflowConditions
- VS.SharePointTools.Workflow.WorkflowList
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 90015dce107eb15859fcb707cc265b84840ca546
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-and-debugging-a-sharepoint-workflow-solution"></a>Návod: Vytváření a ladění řešení pracovního postupu služby SharePoint
  Tento návod ukazuje, jak vytvořit šablonu základní sekvenční pracovní postup. Pracovní postup kontroluje vlastnost knihovny sdílených dokumentů k určení, zda byl revidován dokumentu. Pokud dokument byl revidován, dokončení pracovního postupu.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření projektu služby SharePoint seznamu definice sekvenční pracovní postup v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
-   Vytváření aktivit pracovního postupu.  
  
-   Zpracování události aktivit pracovního postupu.  
  
> [!NOTE]  
>  I když tento návod používá projektu sekvenční pracovní postup, tento proces je stejný jako pro projekt stavu počítače pracovního postupu.  
>   
>  Také váš počítač může zobrazovat odlišné názvy nebo umístění pro některé uživatele, Visual Studio prvky rozhraní v následujících pokynech. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému Microsoft Windows a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="adding-properties-to-the-sharepoint-shared-documents-library"></a>Přidání vlastnosti do SharePoint sdílené knihovny dokumentů  
 Sledovat stav kontroly dokumenty v **sdílené dokumenty** knihovny, vytvoříme tři nové vlastnosti pro sdílené dokumenty na našem webu služby SharePoint: `Status`, `Assignee`, a `Review Comments`. Jsme definovali tyto vlastnosti v **sdílené dokumenty** knihovny.  
  
#### <a name="to-add-properties-to-the-sharepoint-shared-documents-library"></a>Přidání vlastnosti do služby SharePoint sdílené dokumenty knihovny  
  
1.  Otevřete web služby SharePoint, jako je například http://\<název systému > / SitePages/Home.aspx ve webovém prohlížeči.  
  
2.  Na panel Rychlé spuštění, zvolte **SharedDocuments**.  
  
3.  Zvolte **knihovny** na **nástroje knihovny** pásu karet a potom zvolte **vytvořit sloupec** na pásu karet k vytvoření nové sloupce.  
  
4.  Název sloupce **stav dokumentu**, nastavte její typ na **volba (nabídka)**, zadejte následující tři možnosti a pak zvolte **OK** tlačítko:  
  
    -   **Zkontrolujte potřeby**  
  
    -   **Zkontrolujte dokončení**  
  
    -   **Požadované změny**  
  
5.  Vytvořte další dva sloupce a název je **zmocněnec** a **zkontrolovat komentáře**. Nastavte typ sloupce zmocněnec jako jeden řádek textu a typ sloupce zkontrolovat komentáře jako více řádků textu.  
  
## <a name="enabling-documents-to-be-edited-without-requiring-a-check-out"></a>Povolení dokumenty k provádění úprav bez nutnosti vyhradit si  
 Aby bylo jednodušší testovací šablonu pracovního postupu, když upravujete dokumenty bez nutnosti podívejte se na. V dalším postupu můžete nakonfigurovat web služby SharePoint, povolit.  
  
#### <a name="to-enable-documents-to-be-edited-without-checking-them-out"></a>Chcete-li povolit dokumenty k provádění úprav bez rezervovat je  
  
1.  Na panel Rychlé spuštění, zvolte **sdílené dokumenty** odkaz.  
  
2.  Na **nástroje knihovny** pásu karet, vyberte **knihovny** a pak klikněte na příkaz **nastavení knihovny** tlačítko pro zobrazení **nastavení knihovny dokumentů** stránky.  
  
3.  V **obecné nastavení** zvolte **nastavení správy verzí** odkaz zobrazíte **nastavení správy verzí** stránky.  
  
4.  Ověřte, že nastavení **vyžadují dokumenty, které se před provedením úpravami** je **ne**. Pokud není, změňte jej na **ne** a potom zvolte **OK** tlačítko.  
  
5.  Zavřete prohlížeč.  
  
## <a name="creating-a-sharepoint-sequential-workflow-project"></a>Vytvoření projektu sekvenčního pracovního postupu služby SharePoint  
 Sekvenční pracovní postup je sada kroky, které provádí v pořadí, až skončí poslední aktivita. V tomto postupu vytvoříme sekvenční pracovní postup, který se bude vztahovat na našich seznamu Sdílené dokumenty. Pracovní postup Průvodce umožňuje přidružit definici webu nebo v seznamu definici pracovního postupu a umožňuje vám určit, kdy se spustí pracovní postup.  
  
#### <a name="to-create-a-sharepoint-sequential-workflow-project"></a>Vytvoření projektu sekvenčního pracovního postupu služby SharePoint  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu** zobrazíte **nový projekt** dialogové okno.  
  
3.  Rozbalte **SharePoint** uzel v rámci buď **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **2010** uzlu.  
  
4.  V **šablony** podokně, vyberte **projektu služby SharePoint 2010** šablony.  
  
5.  V **název** zadejte **MySharePointWorkflow** a potom zvolte **OK** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
6.  V **zadejte úroveň lokality a zabezpečení pro ladění** vyberte **nasadit jako řešení farmy** možnost tlačítko a potom vyberte **Dokončit** tlačítko tak, aby přijímal úroveň a výchozí web vztah důvěryhodnosti.  
  
     Tento krok nastaví úroveň důvěryhodnosti pro řešení jako řešení farmy, k dispozici jenom možnost pro projekty pracovního postupu. Další informace najdete v tématu [v izolovaném prostoru aspekty řešení](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  V **Průzkumníku řešení**, vyberte uzel projektu a potom na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
8.  V části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
9. V **šablony** podokně, vyberte **sekvenční pracovní postup (pouze řešení farmy)** šablony a potom zvolte **přidat** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
10. V **zadejte název pracovního postupu pro ladění** přijměte výchozí název (**MySharePointWorkflow - Workflow1**). Ponechte výchozí pracovní postup šablony typu hodnotu **pracovní postup seznamu**a potom zvolte **Další** tlačítko.  
  
11. V **chcete Visual Studio automaticky přidružení pracovního postupu v relaci ladění?** vyberte **Další** tlačítko přijměte všechna výchozí nastavení.  
  
     Tento krok automaticky přiřadí pracovního postupu s knihovnou sdílené dokumenty.  
  
12. V **zadejte podmínky pro spuštění pracovního postupu** ponechte výchozí možnosti vybrané v **způsob pracovní postup spustit?** tématu a zvolte **Dokončit** tlačítko.  
  
     Tato stránka umožňuje určit při spuštění pracovního postupu. Ve výchozím nastavení spustí pracovní postup buď když se uživatel ručně spustí v SharePoint nebo při vytvoření nové položky, ke kterému je přidružené pracovního postupu.  
  
## <a name="creating-workflow-activities"></a>Vytváření aktivit pracovního postupu  
 Pracovní postupy obsahují jednu nebo více *aktivity* které představují akce k provedení. Pomocí návrháře pracovních postupů můžete uspořádat aktivity pracovního postupu. V tomto postupu přidáme dvě aktivity do pracovního postupu: Aktivita typu HandleExternalEventActivity a OnWorkFlowItemChanged. Tyto aktivity monitorovat stav kontroly dokumenty v **sdílené dokumenty** seznamu  
  
#### <a name="to-create-workflow-activities"></a>Chcete-li vytvořit aktivity pracovního postupu  
  
1.  Pracovní postup má být zobrazena v Návrháři pracovních postupů. Pokud není, pak otevřete **Workflow1.cs** nebo **Workflow1.vb** v **Průzkumníku řešení**.  
  
2.  V návrháři, vyberte **OnWorkflowActivated1** aktivity.  
  
3.  V **vlastnosti** okno, zadejte **onWorkflowActivated** vedle **Invoked** vlastnost a potom vyberte klávesu Enter.  
  
     Otevře se Editor kódu a metodu obslužné rutiny události s názvem onWorkflowActivated přidají se do souboru kódu Workflow1.  
  
4.  Přepněte zpět na návrháře pracovních postupů, otevřete panel a poté rozbalte **Windows Workflow v3.0** uzlu.  
  
5.  V **Windows Workflow v3.0** uzlu **sada nástrojů**, proveďte jednu z následujících souborů kroků:  
  
    1.  Otevřete místní nabídku pro **při** aktivitu a potom zvolte **kopie**. V Návrháři pracovních postupů otevřete místní nabídku pro řádek v části **onWorkflowActivated1** aktivitu a potom zvolte **vložení**.  
  
    2.  Přetáhněte **při** aktivity z **sada nástrojů** pro návrháře pracovních postupů a připojte se k řádku pod aktivity **onWorkflowActivated1** aktivity.  
  
6.  Vyberte **WhileActivity1** aktivity.  
  
7.  V **vlastnosti** nastavte **podmínky** podmínky kódu.  
  
8.  Rozbalte **podmínku** vlastnost, zadejte **isWorkflowPending** vedle podřízená **podmínku** vlastnost a potom vyberte klávesu Enter.  
  
     Otevře se Editor kódu a metodu s názvem isWorkflowPending přidají se do souboru kódu Workflow1.  
  
9. Přepněte zpět na návrháře pracovních postupů, otevřete panel a poté rozbalte **pracovního postupu služby SharePoint** uzlu.  
  
10. V **pracovního postupu služby SharePoint** uzlu **sada nástrojů**, proveďte jednu z následujících souborů kroků:  
  
    -   Otevřete místní nabídku pro **OnWorkflowItemChanged** aktivitu a potom zvolte **kopie**. V Návrháři pracovních postupů otevřete místní nabídku pro řádek uvnitř **whileActivity1** aktivitu a potom zvolte **vložení**.  
  
    -   Přetáhněte **OnWorkflowItemChanged** aktivity z **sada nástrojů** pro návrháře pracovních postupů a připojte se k řádku uvnitř aktivity **whileActivity1** aktivity.  
  
11. Vyberte **onWorkflowItemChanged1** aktivity.  
  
12. V **vlastnosti** okně nastavte vlastnosti, jak je znázorněno v následující tabulce.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**CorrelationToken**|**workflowToken**|  
    |**Vyvolání**|**onWorkflowItemChanged**|  
  
## <a name="handling-activity-events"></a>Zpracování události aktivit  
 Nakonec zkontrolujte stav dokumentu z každé aktivity. Pokud dokument byl revidován, je dokončení pracovního postupu.  
  
#### <a name="to-handle-activity-events"></a>Zpracování události aktivit  
  
1.  V Workflow1.cs nebo Workflow1.vb, přidat následující pole do horní části `Workflow1` třídy. V tomto poli se používá v aktivitě k určení, jestli po dokončení pracovního postupu.  
  
    ```vb  
    Dim workflowPending As Boolean = True  
    ```  
  
    ```csharp  
    Boolean workflowPending = true;  
    ```  
  
2.  Přidejte následující metodu do `Workflow1` třídy. Tato metoda ověří, hodnota `Document Status` vlastnost seznamu dokumentů k určení, zda byl revidován dokumentu. Pokud `Document Status` je nastavena na `Review Complete`, pak se `checkStatus` metoda nastaví `workflowPending` do **false** k označení, že je připraven k dokončení pracovního postupu.  
  
    ```vb  
    Private Sub checkStatus()  
        If CStr(workflowProperties.Item("Document Status")) = "Review Complete" Then  
            workflowPending = False  
        End If  
    End Sub   
    ```  
  
    ```csharp  
    private void checkStatus()  
    {  
        if ((string)workflowProperties.Item["Document Status"] == "Review Complete")  
        workflowPending = false;  
    }  
    ```  
  
3.  Přidejte následující kód, který `onWorkflowActivated` a `onWorkflowItemChanged` metod k volání `checkStatus` metoda. Při spuštění pracovního postupu, `onWorkflowActivated` volání metod `checkStatus` metoda k určení, jestli má dokument už prohlédli. Pokud nebyl byly zkontrolovány, pracovní postup bude pokračovat. Při ukládání dokumentu `onWorkflowItemChanged` volání metod `checkStatus` metoda znovu k určení, zda byl revidován dokumentu. Při `workflowPending` je nastaveno na **true**, pracovní postup nadále spuštěna.  
  
    ```vb  
    Private Sub onWorkflowActivated(ByVal sender As System.Object, ByVal e As System.Workflow.Activities.ExternalDataEventArgs)  
        checkStatus()  
    End Sub  
  
    Private Sub onWorkflowItemChanged(ByVal sender As System.Object, ByVal e As System.Workflow.Activities.ExternalDataEventArgs)  
        checkStatus()  
    End Sub  
    ```  
  
    ```csharp  
    private void onWorkflowActivated(object sender, ExternalDataEventArgs e)  
    {  
        // Check the status.  
        checkStatus();  
    }  
  
    private void onWorkflowItemChanged(object sender, ExternalDataEventArgs e)  
    {  
        // Check the status.  
        checkStatus();  
    }  
    ```  
  
4.  Přidejte následující kód, který `isWorkflowPending` metodu pro ověření stavu `workflowPending` vlastnost. Pokaždé, když je uložen v dokumentu, **whileActivity1** aktivity volání `isWorkflowPending` metoda. Tato metoda prověří <xref:System.Workflow.Activities.ConditionalEventArgs.Result%2A> vlastnost <xref:System.Workflow.Activities.ConditionalEventArgs> objekt, který chcete určit, zda **WhileActivity1** zůstane nebo dokončení aktivity. Pokud je nastavena na **true**, aktivita dále. Jinak dokončení aktivity a dokončení pracovního postupu.  
  
    ```vb  
    Private Sub isWorkflowPending(ByVal sender As System.Object, ByVal e As System.Workflow.Activities.ConditionalEventArgs)  
        e.Result = workflowPending  
    End Sub  
    ```  
  
    ```csharp  
    private void isWorkflowPending(object sender, ConditionalEventArgs e)  
    {  
        e.Result = workflowPending;  
    }  
    ```  
  
5.  Uložte projekt.  
  
## <a name="testing-the-sharepoint-workflow-template"></a>Testování šabloně pracovního postupu služby SharePoint  
 Při spuštění ladicího programu, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] na serveru SharePoint nasadí šablonu pracovního postupu a přidruží pracovního postupu se **sdílené dokumenty** seznamu. Testování pracovního postupu, spusťte instanci pracovního postupu z dokumentu v **sdílené dokumenty** seznamu.  
  
#### <a name="to-test-the-sharepoint-workflow-template"></a>K testování šablony pracovního postupu služby SharePoint  
  
1.  V Workflow1.cs nebo Workflow1.vb nastavit zarážky vedle **onWorkflowActivated** metoda.  
  
2.  Zvolte klávesy F5 sestavení a spuštění řešení.  
  
     Zobrazí se stránka serveru SharePoint.  
  
3.  V navigačním podokně ve službě SharePoint, vyberte **sdílené dokumenty** odkaz.  
  
4.  V **sdílené dokumenty** vyberte **dokumenty** odkaz na **nástroje knihovny** a pak klikněte na příkaz **odeslat dokument** tlačítko .  
  
5.  V **odeslat dokument** dialogovém okně vyberte **Procházet** tlačítko, vyberte všechny souboru dokumentu, vyberte **otevřete** tlačítko a potom vyberte **OK** tlačítko.  
  
     To odešle vybraný dokument do **sdílené dokumenty** seznamu a spustí pracovní postup.  
  
6.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], ověřte, že ladicí program zastaví u zarážky vedle `onWorkflowActivated` metoda.  
  
7.  Zvolte klávesy F5 pro pokračování v provádění.  
  
8.  Můžete změnit nastavení pro zde dokumentu, ale v je ponechte výchozí hodnoty pro nyní výběrem **Uložit** tlačítko.  
  
     Tím se vrátíte do **sdílené dokumenty** stránky výchozí web služby SharePoint.  
  
9. V **sdílené dokumenty** ověřte, zda hodnota pod **MySharePointWorkflow - Workflow1** sloupec je nastavený na **probíhá**. To znamená, že pracovní postup probíhá a že dokument čeká na zkontrolujte.  
  
10. V **sdílené dokumenty** stránce zvolte dokumentu a potom vyberte šipku, která se zobrazí a potom vyberte **upravit vlastnosti** položku nabídky.  
  
11. Nastavit **stav dokumentu** k **zkontrolujte dokončení**a potom zvolte **Uložit** tlačítko.  
  
     Tím se vrátíte do **sdílené dokumenty** stránky výchozí web služby SharePoint.  
  
12. V **sdílené dokumenty** ověřte, zda hodnota pod **stav dokumentu** sloupec je nastavený na **zkontrolujte dokončení**. Obnovit **sdílené dokumenty** stránky a ověřte, že hodnota pod **MySharePointWorkflow - Workflow1** sloupec je nastavený na **dokončeno**. Znamená to, že po dokončení pracovního postupu a že byl revidován dokumentu.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak vytvořit pracovní postup šablony z těchto témat:  
  
-   Další informace o aktivitách pracovního postupu služby SharePoint, v tématu [aktivity pracovního postupu pro SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkId=178992).  
  
-   Další informace o aktivitách modelu Windows Workflow Foundation, najdete v části [System.Workflow.Activities Namespace](http://go.microsoft.com/fwlink/?LinkId=178993).  
  
## <a name="see-also"></a>Viz také  
 [Vytváření řešení pracovního postupu služby SharePoint](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [Projektu služby SharePoint a šablony položek projektu](../sharepoint/sharepoint-project-and-project-item-templates.md)   
 [Sestavování a ladění řešení služby SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
  
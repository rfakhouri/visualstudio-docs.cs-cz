---
title: "Návod: Vytvoření pracovního postupu pomocí formulářů přidružení a inicializace | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- SharePoint development in Visual Studio, workflow association forms
- workflows [SharePoint development in Visual Studio]
- association forms [SharePoint development in Visual Studio]
- initiation forms [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, workflow initiation forms
ms.assetid: c8666d8c-b173-4245-8014-9c1cd6acb071
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: aa95c519ab24ba042b6a1adfa71c64499b18d4c9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-workflow-with-association-and-initiation-forms"></a>Návod: Vytvoření pracovního postupu pomocí formulářů přidružení a inicializace
  Tento návod ukazuje, jak vytvořit základní sekvenční pracovní postup, která zahrnuje použití formulářů přidružení a inicializace. Jedná se o ASPX formulářů, které umožňují parametry mají být přidány do pracovního postupu, pokud je první přidružená správcem služby SharePoint (formulář přidružení) a při spuštění pracovního postupu uživatelem (formulář spuštění).  
  
 Tento návod popisuje scénář, kde uživatel chce vytvořit pracovní postup schválení pro vyúčtování který má následující požadavky:  
  
-   Když pracovní postup je přidružen seznam, správce se zobrazí výzva s formuláře přidružení, kde zadat dolaru limit pro vyúčtování.  
  
-   Zaměstnanci nahrát jejich vyúčtování do seznamu Sdílené dokumenty, spustit workflow a potom zadejte náklady celkem formuláře inicializace pracovního postupu.  
  
-   Pokud sestavu výdajů zaměstnanec celkový překračuje limit předdefinované správce, úloha se vytvoří pro zaměstnance správce ke schválení vyúčtování. Pokud celkový počet sestav výdajů zaměstnance je menší než nebo rovna hodnotě limitu náklady, zprávu schvalovat automaticky zapsána do seznamu historie pracovního postupu.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření projektu služby SharePoint seznamu definice sekvenční pracovní postup v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
-   Vytvoření plánu pracovního postupu.  
  
-   Zpracování události aktivit pracovního postupu.  
  
-   Vytváření formulářů přidružení a inicializace pracovního postupu.  
  
-   Přidružení pracovního postupu.  
  
-   Ruční spuštění pracovního postupu.  
  
> [!NOTE]  
>  I když tento návod používá projekt sekvenčního pracovního postupu, proces je stejný pro pracovní postupy stav počítače.  
>   
>  Kromě toho, že váš počítač může zobrazovat odlišné názvy nebo umístění některých [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] prvky uživatelského rozhraní v následujících pokynech. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Edici, která máte a nastavení, které používáte, určují tyto prvky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="creating-a-sharepoint-sequential-workflow-project"></a>Vytvoření projektu sekvenčního pracovního postupu služby SharePoint  
 Nejprve vytvořte projekt sekvenčního pracovního postupu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Sekvenční pracovní postup je sérii kroků, které provádí v pořadí, až skončí poslední aktivita. V tomto postupu vytvoříte sekvenční pracovní postup, který se vztahuje na seznamu sdílených dokumentů ve službě SharePoint. Průvodce pracovního postupu umožňuje přidružit webu nebo v seznamu definici pracovního postupu a umožňuje vám určit, kdy se spustí pracovní postup.  
  
#### <a name="to-create-a-sharepoint-sequential-workflow-project"></a>Vytvoření projektu sekvenčního pracovního postupu služby SharePoint  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu** zobrazíte **nový projekt** dialogové okno.  
  
2.  Rozbalte **SharePoint** uzel v rámci buď **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **2010** uzlu.  
  
3.  V **šablony** podokně, vyberte **projektu služby SharePoint 2010** šablona projektu.  
  
4.  V **název** zadejte **ExpenseReport** a potom zvolte **OK** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
5.  V **zadejte úroveň lokality a zabezpečení pro ladění** vyberte **nasadit jako řešení farmy** možnost tlačítko a potom vyberte **Dokončit** tlačítko tak, aby přijímal úroveň a výchozí web vztah důvěryhodnosti.  
  
     Tento krok také nastaví úroveň důvěryhodnosti pro řešení jako řešení farmy, která je k dispozici jenom možnost pro projekty pracovního postupu.  
  
6.  V **Průzkumníku**, vyberte uzel projektu.  
  
7.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
8.  V části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
9. V **šablony** podokně vyberte **sekvenční pracovní postup (pouze řešení farmy)** šablony a potom zvolte **přidat** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
10. V **zadejte název pracovního postupu pro ladění** přijměte výchozí název (**ExpenseReport - Workflow1**). Ponechte výchozí hodnotu typu šablony pracovního postupu (**pracovní postup seznamu)**. Vyberte **Další** tlačítko.  
  
11. V **chcete Visual Studio automaticky přidružení pracovního postupu v relaci ladění?** zrušte zaškrtnutí pole, která automaticky přiřadí šablony pracovního postupu, pokud je zaškrtnuto.  
  
     Tento krok umožňuje ručně přidružení pracovního postupu s později na seznamu Sdílené dokumenty, které zobrazí formulář přidružení.  
  
12. Vyberte **Dokončit** tlačítko.  
  
## <a name="adding-an-association-form-to-the-workflow"></a>Přidání formuláře přidružení do pracovního postupu  
 Dále vytvořte. Formuláře přidružení ASPX, který se zobrazí, když správce služby SharePoint přidruží dokument zprávy o nákladech nejprve pracovního postupu.  
  
#### <a name="to-add-an-association-form-to-the-workflow"></a>Chcete-li přidat formuláře přidružení do pracovního postupu  
  
1.  Vyberte **Workflow1** uzlu v **Průzkumníku řešení**.  
  
2.  Na řádku nabídek zvolte **projektu**, **přidat novou položku** zobrazíte **přidat novou položku** dialogové okno.  
  
3.  V dialogovém okně pole stromové zobrazení, rozbalte položku buď **Visual C#** nebo **jazyka Visual Basic** (v závislosti na vaší jazyk projektu), rozbalte položku **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
4.  V seznamu šablon, vyberte **formuláře přidružení pracovního postupu** šablony.  
  
5.  V **název** textové pole, zadejte **ExpenseReportAssocForm.aspx**.  
  
6.  Vyberte **přidat** tlačítko pro přidání formuláře do projektu.  
  
## <a name="designing-and-coding-the-association-form"></a>Navrhování a kódování formuláře přidružení  
 V tomto postupu zavést funkce formuláře přidružení přidáním ovládacími prvky a kódem na ni.  
  
#### <a name="to-design-and-code-the-association-form"></a>Návrh a kód formuláře přidružení  
  
1.  Ve formuláři přidružení (ExpenseReportAssocForm.aspx), vyhledejte `asp:Content` element, který má `ID="Main"`.  
  
2.  Přímo po prvním řádku v tomto obsahu elementu, přidejte následující kód k vytvoření popisek a textové pole, které vyzve k zadání limit schválení náklady (*AutoApproveLimit*):  
  
    ```  
    <asp:Label ID="lblAutoApproveLimit" Text="Auto Approval Limit:" runat="server" />  
  
    <asp:TextBox ID="AutoApproveLimit" runat="server" />  
    <br /><br />  
    ```  
  
3.  Rozbalte **ExpenseReportAssocForm.aspx** souboru v **Průzkumníku řešení** zobrazíte jeho závislých souborů.  
  
    > [!NOTE]  
    >  Pokud je váš projekt v [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)], musíte zvolit **zobrazit všechny soubory** tlačítko k provedení tohoto kroku.  
  
4.  Otevřete místní nabídku pro soubor ExpenseReportAssocForm.aspx a zvolte **kód zobrazení**.  
  
5.  Nahraďte `GetAssociationData` metodu se:  
  
    ```vb  
    Private Function GetAssociationData() As String  
        ' TODO: Return a string that contains the association data that   
        ' will be passed to the workflow. Typically, this is in XML   
        ' format.  
        Return Me.AutoApproveLimit.Text  
    End Function  
    ```  
  
    ```csharp  
    private string GetAssociationData()  
    {  
        // TODO: Return a string that contains the association data that   
        // will be passed to the workflow. Typically, this is in XML   
        // format.  
        return this.AutoApproveLimit.Text;  
    }  
    ```  
  
## <a name="adding-an-initiation-form-to-the-workflow"></a>Přidávání do spouštěcího formuláře do pracovního postupu  
 Dále vytvořte inicializačního formuláře, který se zobrazí, když uživatelé spustí pracovní postup před jejich vyúčtování.  
  
#### <a name="to-create-an-initiation-form"></a>K vytvoření inicializačního formuláře  
  
1.  Vyberte **Workflow1** uzlu v **Průzkumníku řešení**.  
  
2.  Na řádku nabídek zvolte **projektu**, **přidat novou položku** zobrazení **přidat novou položku** dialogové okno.  
  
3.  V dialogovém okně pole stromové zobrazení, rozbalte položku buď **Visual C#** nebo **jazyka Visual Basic** (v závislosti na vaší jazyk projektu), rozbalte položku **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
4.  V seznamu šablon, vyberte **formuláře inicializace pracovního postupu** šablony.  
  
5.  V **název** textové pole, zadejte **ExpenseReportInitForm.aspx**.  
  
6.  Vyberte **přidat** tlačítko pro přidání formuláře do projektu.  
  
## <a name="designing-and-coding-the-initiation-form"></a>Navrhování a kódování inicializačního formuláře  
 V dalším kroku zavést funkce formuláře inicializace přidáním ovládacími prvky a kódem na ni.  
  
#### <a name="to-code-the-initiation-form"></a>Kód inicializačního formuláře  
  
1.  Ve formuláři spuštění (ExpenseReportInitForm.aspx), vyhledejte `asp:Content` elementu, který obsahuje `ID="Main"`.  
  
2.  Přímo po prvním řádku v tomto obsahu elementu, přidejte následující kód k vytvoření popisek a textové pole, které zobrazí limit schválení náklady (*AutoApproveLimit*), byl zadán ve formuláři přidružení a jiný popisek a textové pole pro zadání celkové náklady (*ExpenseTotal*):  
  
    ```  
    <asp:Label ID="lblAutoApproveLimit" Text="Auto Approval Limit:" runat="server" />  
  
    <asp:TextBox ID="AutoApproveLimit" ReadOnly="true" runat="server" />  
    <br /><br />  
    <asp:Label ID="lblExpenseTotal" Text="Expense Total:" runat="server" />  
  
    <asp:TextBox ID="ExpenseTotal" runat="server" />  
    <br /><br />  
    ```  
  
3.  Rozbalte **ExpenseReportInitForm.aspx** souboru v **Průzkumníku řešení** zobrazíte jeho závislých souborů.  
  
4.  Otevřete místní nabídku pro soubor ExpenseReportInitForm.aspx a zvolte **kód zobrazení**.  
  
5.  Nahraďte `Page_Load` metoda s v následujícím příkladu:  
  
    ```vb  
    Protected Sub Page_Load(ByVal sender As Object, ByVal e As   
      EventArgs) Handles Me.Load  
        InitializeParams()  
        Me.AutoApproveLimit.Text = workflowList.WorkflowAssociations(New   
          Guid(associationGuid)).AssociationData  
        ' Optionally, add code here to pre-populate your form fields.  
    End Sub  
    ```  
  
    ```csharp  
    protected void Page_Load(object sender, EventArgs e)  
    {  
        InitializeParams();  
        this.AutoApproveLimit.Text =   
          workflowList.WorkflowAssociations[new   
          Guid(associationGuid)].AssociationData;  
    }  
    ```  
  
6.  Nahraďte `GetInitiationData` metoda s v následujícím příkladu:  
  
    ```vb  
    ' This method is called when the user clicks the button to start the workflow.  
    Private Function GetInitiationData() As String  
        Return Me.ExpenseTotal.Text  
        ' TODO: Return a string that contains the initiation data that   
        ' will be passed to the workflow. Typically, this is in XML   
        ' format.  
        Return String.Empty  
    End Function  
    ```  
  
    ```csharp  
    // This method is called when the user clicks the button to start the workflow.          
    private string GetInitiationData()  
    {  
        // TODO: Return a string that contains the initiation data that   
        // will be passed to the workflow. Typically, this is in XML   
        // format.  
        return this.ExpenseTotal.Text;  
    }  
    ```  
  
## <a name="customizing-the-workflow"></a>Přizpůsobení pracovního postupu  
 Dále přizpůsobte pracovního postupu. Později kterou přidružíte dvě formy do pracovního postupu.  
  
#### <a name="to-customize-the-workflow"></a>Chcete-li přizpůsobit pracovního postupu  
  
1.  Zobrazení pracovního postupu v Návrháři pracovních postupů otevřením Workflow1 v projektu.  
  
2.  V **sada nástrojů**, rozbalte **v3.0 Windows Workflow** uzlu a vyhledejte **IfElse** aktivity.  
  
3.  Přidejte tuto aktivitu do pracovního postupu pomocí jedné z následujících kroků:  
  
    -   Otevřete místní nabídku pro **IfElse** aktivitu, zvolte **kopie**, otevřete místní nabídku pro řádek v části **onWorkflowActivated1** aktivity v Návrháři pracovních postupů a potom zvolte **vložení**.  
  
    -   Přetáhněte **IfElse** aktivity z **sada nástrojů**a připojte ho k řádku pod **onWorkflowActiviated1** aktivity v Návrháři pracovních postupů.  
  
4.  V sadě nástrojů, rozbalte **pracovního postupu služby SharePoint** uzlu a najděte **createtask –** aktivity.  
  
5.  Přidejte tuto aktivitu do pracovního postupu pomocí jedné z následujících kroků:  
  
    -   Otevřete místní nabídku pro **createtask –** aktivitu, zvolte **kopie**, otevřete místní nabídku pro jednu ze dvou **vyřadit aktivity sem** oblasti v rámci  **IfElseActivity1** v Návrháři pracovních postupů a potom zvolte **vložení**.  
  
    -   Přetáhněte **createtask –** aktivity z **sada nástrojů** na jednu ze dvou **vyřadit aktivity sem** oblasti v rámci **IfElseActivity1**.  
  
6.  V **vlastnosti** okno, zadejte hodnotu vlastnosti o *taskToken* pro **CorrelationToken** vlastnost.  
  
7.  Rozbalte **CorrelationToken** vlastnost tak, že zvolíte na symbol plus (![TreeView plus](../sharepoint/media/plus.gif "TreeView plus")) vedle sebe.  
  
8.  Zvolit na šipku rozevíracího seznamu **hodnota vlastnosti OwnerActivityName** sub vlastnost a nastavte *Workflow1* hodnotu.  
  
9. Vyberte **TaskId** vlastnost a klikněte na tlačítko se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET – Návrhář mobilních řešení elipsy")) tlačítko pro zobrazení **Vazby vlastnosti** dialogové okno.  
  
10. Vyberte **vytvořit vazbu na nový člen** , zvolte **vytvořit pole** možnost tlačítko a potom vyberte **OK** tlačítko.  
  
11. Vyberte **TaskProperties** vlastnost a klikněte na tlačítko se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET – Návrhář mobilních řešení elipsy")) tlačítko pro zobrazení  **Vytvořit vazbu vlastnosti** dialogové okno.  
  
12. Vyberte **vytvořit vazbu na nový člen** , zvolte **vytvořit pole** možnost tlačítko a potom vyberte **OK** tlačítko.  
  
13. V **sada nástrojů**, rozbalte **pracovního postupu služby SharePoint** uzel a vyhledejte **LogToHistoryListActivity** aktivity.  
  
14. Přidejte tuto aktivitu do pracovního postupu pomocí jedné z následujících kroků:  
  
    -   Otevřete místní nabídku pro **LogToHistoryListActivity** aktivitu, zvolte **kopie**, otevřete místní nabídku pro druhý **vyřadit aktivity sem** oblasti v rámci **IfElseActivity1** v Návrháři pracovních postupů a potom zvolte **vložení**.  
  
    -   Přetáhněte **LogToHistoryListActivity** aktivity z **sada nástrojů**a umístěte jej do dalších **vyřadit aktivity sem** oblasti v rámci **IfElseActivity1** .  
  
## <a name="adding-code-to-the-workflow"></a>Přidání kódu do pracovního postupu  
 Dál přidejte kód pracovního postupu pro ni funkce.  
  
#### <a name="to-add-code-to-the-workflow"></a>Chcete-li přidat kód do pracovního postupu  
  
1.  Otevřete místní nabídku pro **createTask1** aktivity v Návrháři pracovních postupů a potom zvolte **kód zobrazení**.  
  
2.  Přidejte následující metodu:  
  
    ```vb  
    Private Sub createTask1_MethodInvoking(ByVal sender As   
      System.Object, ByVal e As System.EventArgs)  
        createTask1_TaskId1 = Guid.NewGuid  
        createTask1_TaskProperties1.AssignedTo = "somedomain\\someuser"  
        createTask1_TaskProperties1.Description = "Please approve the   
          expense report"  
        createTask1_TaskProperties1.Title = "Expense Report Approval   
          Needed"  
    End Sub   
    ```  
  
    ```csharp  
    private void createTask1_MethodInvoking(object sender, EventArgs e)  
    {  
        createTask1_TaskId1 = Guid.NewGuid();  
        createTask1_TaskProperties1.AssignedTo = "somedomain\\someuser";  
        createTask1_TaskProperties1.Description = "Please approve the   
          expense report";  
        createTask1_TaskProperties1.Title = "Expense Report Approval   
          Needed";  
    }   
    ```  
  
    > [!NOTE]  
    >  V kódu, nahraďte `somedomain\\someuser` s doména a uživatelské jméno, pro který úloha bude vytvořen, jako je třeba "`Office\\JoeSch`". Pro testování je nejjednodušší použít účet, který vyvíjíte s.  
  
3.  Níže `MethodInvoking` metody přidat v následujícím příkladu:  
  
    ```vb  
    Private Sub checkApprovalNeeded(ByVal sender As Object, ByVal e As   
      ConditionalEventArgs)  
        Dim approval As Boolean = False  
        If (Convert.ToInt32(workflowProperties.InitiationData) >   
          Convert.ToInt32(workflowProperties.AssociationData)) Then  
            approval = True  
        End If  
        e.Result = approval  
    End Sub   
    ```  
  
    ```csharp  
    private void checkApprovalNeeded(object sender, ConditionalEventArgs   
      e)  
    {  
        bool approval = false;  
        if (Convert.ToInt32(workflowProperties.InitiationData) >   
          Convert.ToInt32(workflowProperties.AssociationData))  
        {  
            approval = true;  
        }  
        e.Result = approval;  
    }   
    ```  
  
4.  V Návrháři pracovních postupů, vyberte **ifElseBranchActivity1** aktivity.  
  
5.  V **vlastnosti** okně vyberte šipku rozevíracího seznamu **podmínku** vlastnost a potom nastavte *kód stavu* hodnotu.  
  
6.  Rozbalte **podmínku** vlastnost tak, že zvolíte na symbol plus (![TreeView plus](../sharepoint/media/plus.gif "TreeView plus")) vedle sebe a pak jeho hodnotu nastavte *checkApprovalNeeded* .  
  
7.  V Návrháři pracovních postupů otevřete místní nabídku pro **logToHistoryListActivity1** aktivitu a potom vyberte **Generovat obslužné rutiny** ke generování pro metodu prázdný `MethodInvoking` událostí.  
  
8.  Nahraďte `MethodInvoking` kódu pomocí následující:  
  
    ```vb  
    Private Sub logToHistoryListActivity1_MethodInvoking(ByVal sender As   
      System.Object, ByVal e As System.EventArgs)  
        Me.logToHistoryListActivity1.HistoryOutcome = ("Expense was auto   
          approved for " + workflowProperties.InitiationData)  
    End Sub   
    ```  
  
    ```csharp  
    private void logToHistoryListActivity1_MethodInvoking(object sender,   
      EventArgs e)  
    {  
        this.logToHistoryListActivity1.HistoryOutcome = "Expense was   
          auto approved for " + workflowProperties.InitiationData;  
    }   
    ```  
  
9. Zvolte klávesy F5 k ladění programu.  
  
     To kompilaci aplikace, balíčky jej, pak ji nasadí, aktivuje jeho funkce, recykluje [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] fond aplikací a poté spustí prohlížeč v umístění zadané v **adresa Url webu** vlastnost.  
  
## <a name="associating-the-workflow-to-the-documents-list"></a>Přidružení pracovního postupu do seznamu dokumentů  
 V dalším kroku zobrazení formuláře přidružení pracovního postupu tím, že přidružíte pracovního postupu se **SharedDocuments** seznamu na web služby SharePoint.  
  
#### <a name="to-associate-the-workflow"></a>Chcete-li přidružit pracovního postupu  
  
1.  Vyberte **sdílené dokumenty** odkaz na panel Rychlé spuštění.  
  
2.  Vyberte **knihovny** odkaz na **nástroje knihovny** a pak klikněte na příkaz **nastavení knihovny** tlačítko pásu karet.  
  
3.  V **oprávnění a správa** zvolte **nastavení pracovních postupů** propojit a potom zvolte **přidat pracovní postup** odkaz na **pracovních** stránky.  
  
4.  V horním seznamu na stránce nastavení pracovního postupu, vyberte **ExpenseReport - Workflow1** šablony.  
  
5.  V poli Další zadejte **ExpenseReportWorkflow** a potom zvolte **Další** tlačítko.  
  
     To přiřadí pracovního postupu se **sdílené dokumenty** seznamu a zobrazí formuláře přidružení pracovního postupu.  
  
6.  V **Limit pro automatické schvalování** text zadejte **1200** a potom zvolte **přidružení pracovního postupu** tlačítko.  
  
## <a name="starting-the-workflow"></a>Spuštění pracovního postupu  
 V dalším kroku přidružení pracovního postupu do jednoho z dokumentů v **sdílené dokumenty** seznamu zobrazíte formuláře inicializace pracovního postupu.  
  
#### <a name="to-start-the-workflow"></a>Spustit pracovní postup  
  
1.  Na stránce služby SharePoint, vyberte **Domů** tlačítko.  
  
2.  Vyberte **sdílené dokumenty** odkaz na panel Rychlé spuštění zobrazíte **sdílené dokumenty** seznamu.  
  
3.  Vyberte **dokumenty** odkaz na **knihovny nástroje** v horní části stránky a potom vyberte **odeslat dokument** na pásu karet nahrát nový dokument do **Sdílené dokumenty** seznamu.  
  
4.  V **odeslat dokument** dialogovém okně vyberte **Procházet** tlačítko, vyberte všechny souboru dokumentu, vyberte **otevřete** tlačítko a potom vyberte **OK** tlačítko.  
  
     Můžete změnit nastavení pro dokument v tomto dialogovém, ale je v ponechte výchozí hodnoty tak, že zvolíte **Uložit** tlačítko.  
  
5.  Zvolte nahrané dokumentu a potom vyberte šipku rozevíracího seznamu, který se zobrazí a potom vyberte **pracovních** položky.  
  
6.  Vyberte bitovou kopii vedle ExpenseReportWorkflow.  
  
     Zobrazí se formuláře inicializace pracovního postupu. (Všimněte si, že hodnota zobrazena v **Limit pro automatické schvalování** pole je jen pro čtení, protože byl zadán ve formuláři přidružení.)  
  
7.  V **celkové náklady** text zadejte **1 600**a potom zvolte **spustit pracovní postup** tlačítko.  
  
     Zobrazí se **sdílené dokumenty** seznamu znovu. Nový sloupec s názvem **ExpenseReportWorkflow** s hodnotou **dokončeno** se přidá do položky pracovního postupu je právě spuštěna.  
  
8.  Zvolte na šipku rozevíracího seznamu vedle nahrané dokumentu a pak **pracovních** položku si můžete zobrazit na stavové stránce pracovního postupu. Vyberte **dokončeno** hodnoty v části **dokončit pracovní postupy**. Úloha je uveden v části **úlohy** části.  
  
9. Zvolte název úlohy zobrazíte její podrobnosti úlohy.  
  
10. Přejděte zpět **SharedDocuments** seznamu a restartujte pracovní postup, pomocí stejného dokumentu nebo jiný.  
  
11. Zadejte dobu spuštění stránky, která je menší než nebo rovna výše uvedených na stránce přidružení (**1200**).  
  
     V takovém případě se místo úlohu vytvoří položku v seznamu historie. Zobrazí položky v **historie pracovního postupu** části stránky Stav pracovního postupu. Všimněte si zprávy v **výsledek** sloupec Historie událostí. Obsahuje zadaný v text `logToHistoryListActivity1.MethodInvoking` událost, která zahrnuje dobu, která byla schvalovat automaticky.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak vytvořit pracovní postup šablony z těchto témat:  
  
-   Další informace o pracovních postupů služby SharePoint, najdete v části [pracovních postupů v služby Windows SharePoint Services](http://go.microsoft.com/fwlink/?LinkID=166275).  
  
## <a name="see-also"></a>Viz také  
 [Vytváření řešení pracovního postupu služby SharePoint](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [Návod: Přidání stránky aplikace do pracovního postupu](../sharepoint/walkthrough-add-an-application-page-to-a-workflow.md)  
  
  
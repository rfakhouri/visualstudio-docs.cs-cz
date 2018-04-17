---
title: 'Návod: Přidání stránky aplikace do pracovního postupu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, adding applications page to workflow
- application page [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 97c720ded65e46e85f8d9f20f9f509b31f2cebbb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-add-an-application-page-to-a-workflow"></a>Návod: Přidání stránky aplikace do pracovního postupu
  Tento návod ukazuje, jak přidat stránku aplikace, která zobrazuje data odvozené z pracovního postupu projektu pracovního postupu. Vychází projektu popsané v tématu [návod: vytvoření pracovního postupu pomocí formulářů přidružení a inicializace](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).  
  
 Tento návod ukazuje následující úlohy:  
  
-   Přidání stránky ASPX aplikace do projektu pracovního postupu služby SharePoint.  
  
-   Získání dat z projektu workflow a manipulace s nimi ho.  
  
-   Zobrazení dat v tabulce na stránce aplikace.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
-   Je třeba také provést na projekt v tématu [návod: vytvoření pracovního postupu pomocí formulářů přidružení a inicializace](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).  
  
## <a name="amending-the-workflow-code"></a>Změnu kód pracovního postupu  
 Nejprve přidejte řádek kódu do pracovního postupu k nastavení hodnoty sloupce výsledek na množství vyúčtování. Tato hodnota se používá novější při výpočtu souhrnné sestavy výdajů.  
  
#### <a name="to-set-the-value-of-the-outcome-column-in-the-workflow"></a>Chcete-li nastavit hodnotu pro sloupec výsledek v pracovním postupu  
  
1.  Načtení dokončené projektu v tématu [návod: vytvoření pracovního postupu pomocí formulářů přidružení a inicializace](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Otevřete kód pro Workflow1.cs nebo Workflow1.vb (v závislosti na programovacího jazyka).  
  
3.  V dolní části `createTask1_MethodInvoking` metoda, přidejte následující kód:  
  
    ```vb  
    createTask1_TaskProperties1.ExtendedProperties("Outcome") =   
      workflowProperties.InitiationData  
    ```  
  
    ```csharp  
    createTask1_TaskProperties1.ExtendedProperties["Outcome"] =   
      workflowProperties.InitiationData;  
    ```  
  
## <a name="creating-an-application-page"></a>Vytvoření stránky aplikace  
 Formuláře ASPX v dalším kroku přidejte do projektu. Tento formulář se zobrazí data získaná z projektu výdajů sestavy pracovního postupu. K tomuto účelu přidáte stránky aplikace. Stránky aplikace používá stejnou stránku předlohy jako ostatní stránky služby SharePoint, což znamená, že bude vypadat podobně jako jiné stránky na web služby SharePoint.  
  
#### <a name="to-add-an-application-page-to-the-project"></a>Přidání stránky aplikace do projektu  
  
1.  Zvolte ExpenseReport projekt a potom na panelu nabídek **projektu**, **přidat novou položku**.  
  
2.  V **šablony** podokně, vyberte **stránky aplikace** šablony, použít výchozí název položky projektu (**ApplicaitonPage1.aspx**) a vyberte **Přidat** tlačítko.  
  
3.  V [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] z ApplicationPage1.aspx, nahraďte `PlaceHolderMain` oddíl následujícím kódem:  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
        <asp:Label ID="Label1" runat="server" Font-Bold="True"   
            Text="Expenses that exceeded allotted amount" Font-Size="Medium"></asp:Label>  
        <br />  
        <asp:Table ID="Table1" runat="server">  
        </asp:Table>  
    </asp:Content>  
    ```  
  
     Tento kód přidá na stránku společně s název tabulky.  
  
4.  Přidejte název stránky aplikace tak, že nahradíte `PlaceHolderPageTitleInTitleArea` oddíl následujícím kódem:  
  
    ```  
    <asp:Content ID="PageTitleInTitleArea" ContentPlaceHolderID="PlaceHolderPageTitleInTitleArea" runat="server" >  
        Expense Report Summary  
    </asp:Content>  
    ```  
  
## <a name="coding-the-application-page"></a>Kódování stránky aplikace  
 Dál přidejte kód na stránku sestavy souhrnu aplikací náklady. Při otevření stránky kontroluje kód seznamu úloh ve službě SharePoint pro vyúčtování nákladů, které překročily přidělené limitu útraty. Tato sestava uvádí jednotlivé položky spolu s součet výdaje.  
  
#### <a name="to-code-the-application-page"></a>Do kódu stránky aplikace  
  
1.  Vyberte **ApplicationPage1.aspx** uzel a potom na řádku nabídek zvolte **zobrazení**, **kód** zobrazíte kódu stránky aplikace.  
  
2.  Nahraďte **pomocí** nebo **Import** příkazy (v závislosti na programovacího jazyka) v horní části třídy následujícím kódem:  
  
    ```vb  
    Imports System  
    Imports Microsoft.SharePoint  
    Imports Microsoft.SharePoint.WebControls  
    Imports System.Collections  
    Imports System.Data  
    Imports System.Web.UI  
    Imports System.Web.UI.WebControls  
    Imports System.Web.UI.WebControls.WebParts  
    Imports System.Drawing  
    Imports Microsoft.SharePoint.Navigation  
    ```  
  
    ```csharp  
    using System;  
    using Microsoft.SharePoint;  
    using Microsoft.SharePoint.WebControls;  
    using System.Collections;  
    using System.Data;  
    using System.Web.UI;  
    using System.Web.UI.WebControls;  
    using System.Web.UI.WebControls.WebParts;  
    using System.Drawing;  
    using Microsoft.SharePoint.Navigation;  
    ```  
  
3.  Přidejte následující kód, který `Page_Load` metoda:  
  
    ```vb  
    Try  
        ' Reference the Tasks list on the SharePoint site.  
        ' Replace "TestServer" with a valid SharePoint server name.  
        Dim site As SPSite = New SPSite("http://TestServer")  
        Dim list As SPList = site.AllWebs(0).Lists("Tasks")  
        ' string text = "";  
        Dim sum As Integer = 0  
        Table1.Rows.Clear()  
        ' Add table headers.  
        Dim hr As TableHeaderRow = New TableHeaderRow  
        hr.BackColor = Color.LightBlue  
        Dim hc1 As TableHeaderCell = New TableHeaderCell  
        Dim hc2 As TableHeaderCell = New TableHeaderCell  
        hc1.Text = "Expense Report Name"  
        hc2.Text = "Amount Exceeded"  
        hr.Cells.Add(hc1)  
        hr.Cells.Add(hc2)  
        ' Add the TableHeaderRow as the first item   
        ' in the Rows collection of the table.  
        Table1.Rows.AddAt(0, hr)  
        ' Iterate through the tasks in the Task list and collect those    
        ' that have values in the "Related Content" and "Outcome" fields   
        ' - the fields written to when expense approval is required.  
        For Each item As SPListItem In list.Items  
            Dim s_relContent As String = ""  
            Dim s_outcome As String = ""  
            Try  
                ' Task has the fields - treat as expense report.  
                s_relContent = item.GetFormattedValue("Related Content")  
                s_outcome = item.GetFormattedValue("Outcome")  
            Catch erx As System.Exception  
                ' Task does not have fields - skip it.  
                Continue For  
            End Try  
            ' Convert amount to an int and keep a running total.  
            If (Not String.IsNullOrEmpty(s_relContent) And Not   
              String.IsNullOrEmpty(s_outcome)) Then  
                sum = (sum + Convert.ToInt32(s_outcome))  
                Dim relContent As TableCell = New TableCell  
                relContent.Text = s_relContent  
                Dim outcome As TableCell = New TableCell  
                outcome.Text = ("$" + s_outcome)  
                Dim dataRow2 As TableRow = New TableRow  
                dataRow2.Cells.Add(relContent)  
                dataRow2.Cells.Add(outcome)  
                Table1.Rows.Add(dataRow2)  
            End If  
        Next  
        ' Report the sum of the reports in the table footer.  
        Dim tfr As TableFooterRow = New TableFooterRow  
        tfr.BackColor = Color.LightGreen  
        ' Create a TableCell object to contain the   
        ' text for the footer.  
        Dim ftc1 As TableCell = New TableCell  
        Dim ftc2 As TableCell = New TableCell  
        ftc1.Text = "TOTAL: "  
        ftc2.Text = ("$" + Convert.ToString(sum))  
        ' Add the TableCell object to the Cells  
        ' collection of the TableFooterRow.  
        tfr.Cells.Add(ftc1)  
        tfr.Cells.Add(ftc2)  
        ' Add the TableFooterRow to the Rows  
        ' collection of the table.  
        Table1.Rows.Add(tfr)  
    Catch errx As Exception  
        System.Diagnostics.Debug.WriteLine(("Error: " + errx.ToString))  
    End Try  
    ```  
  
    ```csharp  
    try  
    {  
        // Reference the Tasks list on the SharePoint site.  
        // Replace "TestServer" with a valid SharePoint server name.  
        SPSite site = new SPSite("http://TestServer");  
        SPList list = site.AllWebs[0].Lists["Tasks"];  
  
        // string text = "";  
        int sum = 0;  
  
        Table1.Rows.Clear();  
  
        // Add table headers.  
        TableHeaderRow hr = new TableHeaderRow();  
        hr.BackColor = Color.LightBlue;  
        TableHeaderCell hc1 = new TableHeaderCell();  
        TableHeaderCell hc2 = new TableHeaderCell();  
        hc1.Text = "Expense Report Name";  
        hc2.Text = "Amount Exceeded";  
        hr.Cells.Add(hc1);  
        hr.Cells.Add(hc2);  
        // Add the TableHeaderRow as the first item   
        // in the Rows collection of the table.  
        Table1.Rows.AddAt(0, hr);  
  
        // Iterate through the tasks in the Task list and collect those   
        // that have values in the "Related Content" and "Outcome"   
        // fields - the fields written to when expense approval is   
        // required.  
        foreach (SPListItem item in list.Items)  
        {  
            string s_relContent = "";  
            string s_outcome = "";  
  
            try  
            {  
                // Task has the fields - treat as expense report.  
                s_relContent = item.GetFormattedValue("Related   
                  Content");  
                s_outcome = item.GetFormattedValue("Outcome");  
            }  
            catch  
            {  
                // Task does not have fields - skip it.  
                continue;  
            }  
  
            if (!String.IsNullOrEmpty(s_relContent) &&   
              !String.IsNullOrEmpty(s_outcome))  
            {  
                // Convert amount to an int and keep a running total.  
                sum += Convert.ToInt32(s_outcome);  
                TableCell relContent = new TableCell();  
                relContent.Text = s_relContent;  
                TableCell outcome = new TableCell();  
                outcome.Text = "$" + s_outcome;  
                TableRow dataRow2 = new TableRow();  
                dataRow2.Cells.Add(relContent);  
                dataRow2.Cells.Add(outcome);  
                Table1.Rows.Add(dataRow2);  
            }  
        }  
  
        // Report the sum of the reports in the table footer.  
           TableFooterRow tfr = new TableFooterRow();  
        tfr.BackColor = Color.LightGreen;  
  
        // Create a TableCell object to contain the   
        // text for the footer.  
        TableCell ftc1 = new TableCell();  
        TableCell ftc2 = new TableCell();  
        ftc1.Text = "TOTAL: ";  
        ftc2.Text = "$" + Convert.ToString(sum);  
  
        // Add the TableCell object to the Cells  
        // collection of the TableFooterRow.  
        tfr.Cells.Add(ftc1);  
        tfr.Cells.Add(ftc2);  
  
        // Add the TableFooterRow to the Rows  
        // collection of the table.  
        Table1.Rows.Add(tfr);  
    }  
  
    catch (Exception errx)  
    {  
        System.Diagnostics.Debug.WriteLine("Error: " + errx.ToString());  
    }  
    ```  
  
    > [!WARNING]  
    >  Nezapomeňte nahradit "TestServer" v kódu s názvem platný server se systémem SharePoint.  
  
## <a name="testing-the-application-page"></a>Testování stránky aplikace  
 Dále určete, zda stránka aplikace správně zobrazí data náklady.  
  
#### <a name="to-test-the-application-page"></a>Otestování stránky aplikace  
  
1.  Zvolte klávesy F5 spusťte a nasazení projektu do služby SharePoint.  
  
2.  Vyberte **Domů** tlačítko a potom vyberte **sdílené dokumenty** odkaz na panel Rychlé spuštění k zobrazení seznamu sdílených dokumentů na webu služby SharePoint.  
  
3.  Představují vyúčtování v tomto příkladu, nahrát některé nové dokumenty do seznamu dokumentů výběrem **dokumenty** odkaz na **LibraryTools** v horní části stránky a pak vyberete  **Nahrání dokumentů** na pásu karet nástroje.  
  
4.  Po odeslání některých dokumentů, vytváření instancí pracovního postupu tak, že zvolíte **knihovny** odkaz na **LibraryTools** v horní části stránky a pak vyberete **nastavení knihovny**tlačítko na pásu karet.  
  
5.  V **nastavení knihovny dokumentů** vyberte **nastavení pracovních postupů** na odkaz v **oprávnění a správa** části.  
  
6.  V **nastavení pracovních postupů** vyberte **přidat pracovní postup** odkaz.  
  
7.  V **přidat pracovní postup** vyberte **ExpenseReport - Workflow1** pracovního postupu, zadejte název pracovního postupu, jako například **ExpenseTest**a potom zvolte **Další** tlačítko.  
  
     Formuláře přidružení pracovního postupu se zobrazí. Sestava se používá částka limit výdajů.  
  
8.  Ve formuláři přidružení zadejte **1000** do **Limit pro automatické schvalování** pole a potom vyberte **přidružení pracovního postupu** tlačítko.  
  
9. Vyberte **domácí** tlačítko se vraťte na domovskou stránku služby SharePoint.  
  
10. Vyberte **sdílené dokumenty** odkaz na panel Rychlé spuštění.  
  
11. Vyberte jednu z nahrávat dokumenty, které se zobrazí rozevírací šipku, zvolte jej a potom zvolte **pracovních** položky.  
  
12. Vyberte bitovou kopii vedle ExpenseTest k zobrazení formuláře inicializace pracovního postupu.  
  
13. V **celkové náklady** textového pole zadejte hodnotu, která je větší než 1 000 a potom zvolte **spustit pracovní postup** tlačítko.  
  
     Když hlášené výdajů překračuje velikost přidělené náklady, úloha se přidá do seznamu úkolů. Sloupec s názvem **ExpenseTest** s hodnotou **dokončeno** je taky přidaný ke náklady položky sestavy v seznamu Sdílené dokumenty.  
  
14. Opakujte kroky 11 13 s jinými dokumenty v seznamu Sdílené dokumenty. (Přesný počet dokumentů, není důležité.)  
  
15. Zobrazení stránky Souhrn aplikace náklady sestavu otevřením následující adresu URL ve webovém prohlížeči: **http://***SystemName***/_layouts/ExpenseReport/ApplicationPage1.aspx**.  
  
     Na stránce Souhrn sestavy výdajů obsahuje seznam všech sestav výdajů, které překročil přidělenou velikost, velikost, překročení ho pomocí a celkovou velikost pro všechny sestavy.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o stránek aplikací služby SharePoint, naleznete v části [vytváření stránek aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).  
  
 Se více o tom, jak navrhnout obsahu stránce služby SharePoint pomocí návrháře Visual Web v sadě Visual Studio z těchto témat:  
  
-   [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md).  
  
-   [Vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření pracovního postupu pomocí formulářů přidružení a inicializace](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)   
 [Postupy: vytvoření stránky aplikace](../sharepoint/how-to-create-an-application-page.md)   
 [Vytváření stránek aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  
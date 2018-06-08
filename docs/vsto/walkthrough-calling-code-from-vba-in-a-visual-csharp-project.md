---
title: 'Návod: Volání kódu z jazyka VBA v projektu jazyka Visual C#'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel [Office development in Visual Studio], calling code from VBA
- Word [Office development in Visual Studio], calling code from VBA
- Visual C# [Office development in Visual Studio], calling code from VBA
- workbooks [Office development in Visual Studio], calling code from VBA
- VBA [Office development in Visual Studio], calling code in document-level customizations
- Office documents [Office development in Visual Studio, Visual Basic for Applications and
- calling code from VBA
- document-level customizations [Office development in Visual Studio], calling code
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e2803ef31ec1009215d4490ac527c42cbdc90571
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845474"
---
# <a name="walkthrough-call-code-from-vba-in-a-visual-c-project"></a>Návod: Volání kódu z jazyka VBA v projektu jazyka Visual C#
  Tento návod ukazuje, jak volat metodu přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Excel z jazyka Visual Basic pro aplikace (VBA) kód do sešitu. Postup zahrnuje tři základní kroky: Přidejte metodu k `Sheet1` položky třída hostitele, vystavit metodu VBA pro vytváření kódu v sešitu a potom volejte metodu z kódu jazyka VBA v sešitu.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 I když tento návod používá Excel konkrétně, koncepty ukázán podle návodu se rovněž vztahují na projekty na úrovni dokumentu ve Wordu.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření sešitu, který obsahuje VBA kód.  
  
-   Důvěřující umístění sešitu s použitím v Centru zabezpečení v aplikaci Excel.  
  
-   Přidání metody do `Sheet1` položky třída hostitele.  
  
-   Extrahování rozhraní pro `Sheet1` položky třída hostitele.  
  
-   Vystavení metody VBA kód.  
  
-   Volání metody z jazyka VBA kód.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Excel  
  
## <a name="create-a-workbook-that-contains-vba-code"></a>Vytvořte sešit, který obsahuje VBA kód  
 Prvním krokem je vytvoření s podporou maker sešit, který obsahuje jednoduché makro VBA pro vytváření. Předtím, než můžete vystavení kódu do vlastního nastavení pro jazyk VBA, sešit musí obsahovat již VBA kód. Visual Studio nelze upravit, jinak hodnota VBA projekt, který má povolení VBA kód provést volání do sestavení vlastní nastavení.  
  
 Pokud již máte sešit, který obsahuje VBA kód, který chcete použít, můžete tento krok přeskočit.  
  
### <a name="to-create-a-workbook-that-contains-vba-code"></a>Chcete-li vytvořit sešit, který obsahuje VBA kód  
  
1.  Spuštění aplikace Excel.  
  
2.  Uloží aktivní dokument jako **Excel Macro-Enabled sešitu (\*.xlsm)** s názvem **WorkbookWithVBA**. Uložte ji do vhodného umístění, jako je například plochy.  
  
3.  Na pásu karet klikněte na **vývojáře** kartě.  
  
    > [!NOTE]  
    >  Pokud **vývojáře** karta není viditelný, musíte ji nejdříve zobrazit. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
4.  V **kód** klikněte na možnost **jazyka Visual Basic**.  
  
     Otevře se Editor jazyka Visual Basic.  
  
5.  V **projektu** okna, klikněte dvakrát na **ThisWorkbook**.  
  
     V souboru kódu `ThisWorkbook` objektu se otevře.  
  
6.  Přidejte následující VBA kód do souboru kódu. Tento kód definuje jednoduché funkci, která se nic nestane. Jediným účelem: Tato funkce je zajistit, že projekt VBA existuje v sešitu. To je potřeba na pozdější kroky v tomto návodu.  
  
    ```vb  
    Sub EmptySub()  
    End Sub  
    ```  
  
7.  Uložte dokument a ukončete aplikaci Excel.  
  
## <a name="create-the-project"></a>Vytvoření projektu  
 Nyní můžete vytvořit projekt na úrovni dokumentu pro Excel, která používá s podporou maker sešit, který jste vytvořili dříve.  
  
### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** a potom rozbalte **Office/SharePoint**.  
  
4.  Vyberte **Office Add in** uzlu.  
  
5.  V seznamu šablon projektu, vyberte **sešitu aplikace Excel 2010** nebo **sešitu aplikace Excel 2013** projektu.  
  
6.  V **název** zadejte **CallingCodeFromVBA**.  
  
7.  Click **OK**.  
  
     **Visual Studio Tools for Office – Průvodce projektem** otevře.  
  
8.  Vyberte **zkopírovat stávající dokument**a v **úplnou cestu stávající dokument** zadejte umístění **WorkbookWithVBA** sešitu, který jste vytvořili dříve . Pokud používáte s podporou maker sešit, zadejte umístění tohoto sešitu.  
  
9. Klikněte na tlačítko **Dokončit**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otevře se **WorkbookWithVBA** sešitu v návrháři a přidá **CallingCodeFromVBA** projektu do **Průzkumníku řešení**.  
  
## <a name="trust-the-location-of-the-workbook"></a>Vztah důvěryhodnosti umístění sešitu  
 Před kódu můžete vystavit ve vašem řešení VBA pro vytváření kódu v sešitu, musí důvěřovat VBA v sešitu ke spuštění. Chcete-li to provést několika způsoby. V tomto návodu se podle důvěřující umístění sešit v provedení této úlohy **Centrum zabezpečení** v aplikaci Excel.  
  
### <a name="to-trust-the-location-of-the-workbook"></a>Důvěřovat umístění sešitu  
  
1.  Spuštění aplikace Excel.  
  
2.  Klikněte **souboru** kartě.  
  
3.  Klikněte **možnosti aplikace Excel** tlačítko.  
  
4.  V podokně kategorie, klikněte na **Centrum zabezpečení**.  
  
5.  V podokně podrobností klikněte na tlačítko **nastavení Centra zabezpečení**.  
  
6.  V podokně kategorie, klikněte na **důvěryhodné umístění**.  
  
7.  V podokně podrobností klikněte na tlačítko **přidat nové umístění**.  
  
8.  V **umístění důvěryhodné Microsoft Office** dialogové okno, přejděte do složky, která obsahuje **CallingCodeFromVBA** projektu.  
  
9. Vyberte **podsložky toto umístění jsou také důvěryhodné**.  
  
10. V **umístění důvěryhodné Microsoft Office** dialogové okno, klikněte na tlačítko **OK**.  
  
11. V **Centrum zabezpečení** dialogové okno, klikněte na tlačítko **OK**.  
  
12. V **možnosti aplikace Excel** dialogové okno, klikněte na tlačítko **OK**.  
  
13. Ukončení **Excel**.  
  
## <a name="add-a-method-to-the-sheet1-class"></a>Přidání metody do Sheet1 – třída  
 Teď, když je projekt VBA nastavili, přidejte veřejnou metodu k `Sheet1` položky třída, kterou můžete volat z kódu VBA pro vytváření hostitele.  
  
### <a name="to-add-a-method-to-the-sheet1-class"></a>Přidání metody do Sheet1 – třída  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Sheet1.cs**a potom klikněte na **kód zobrazení**.  
  
     **Sheet1.cs** soubor se otevře v editoru kódu.  
  
2.  Přidejte následující kód, který `Sheet1` třídy. `CreateVstoNamedRange` Metoda vytvoří novou <xref:Microsoft.Office.Tools.Excel.NamedRange> objekt v zadaném rozsahu. Tato metoda také vytvoří obslužnou rutinu události pro <xref:Microsoft.Office.Tools.Excel.NamedRange.Selected> události <xref:Microsoft.Office.Tools.Excel.NamedRange>. Dále v tomto návodu budete volat `CreateVstoNamedRange` metoda z kódu jazyka VBA v dokumentu.  
  
     [!code-csharp[Trin_CallingCSCustomizationFromVBA#2](../vsto/codesnippet/CSharp/CallingCodeFromVBA/Sheet1.cs#2)]  
  
3.  Přidejte následující metodu do `Sheet1` třídy. Přepíše tuto metodu <xref:Microsoft.Office.Tools.Excel.Worksheet.GetAutomationObject%2A> metoda vrátí aktuální instancí třídy `Sheet1` třídy.  
  
     [!code-csharp[Trin_CallingCSCustomizationFromVBA#3](../vsto/codesnippet/CSharp/CallingCodeFromVBA/Sheet1.cs#3)]  
  
4.  Použít následující atributy před první řádek `Sheet1` deklarace třídy. Tyto atributy zviditelnit třídu do modelu COM, ale bez generování třídy rozhraní.  
  
     [!code-csharp[Trin_CallingCSCustomizationFromVBA#1](../vsto/codesnippet/CSharp/CallingCodeFromVBA/Sheet1.cs#1)]  
  
## <a name="extract-an-interface-for-the-sheet1-class"></a>Extrahování rozhraní pro Sheet1 – třída  
 Předtím, než můžete vystavit `CreateVstoNamedRange` metodu VBA kód, je nutné vytvořit veřejné rozhraní, která definuje tuto metodu, a musí vystavit tohoto rozhraní COM.  
  
### <a name="to-extract-an-interface-for-the-sheet1-class"></a>Extrahování rozhraní pro Sheet1 – třída  
  
1.  V **Sheet1.cs** kódu souboru, klikněte kamkoli do `Sheet1` třídy.  
  
2.  Na **Refaktorovat** nabídky, klikněte na tlačítko **extrahování rozhraní**.  
  
3.  V **extrahování rozhraní** v dialogovém **vyberte veřejné členy do formuláře rozhraní** pole, klikněte na položku `CreateVstoNamedRange` metoda.  
  
4.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] generuje nové rozhraní s názvem `ISheet1`, a upravuje definice `Sheet1` třídy tak, aby se implementuje `ISheet1` rozhraní. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otevře také **ISheet1.cs** souboru v editoru kódu.  
  
5.  V **ISheet1.cs** souboru, nahraďte `ISheet1` rozhraní deklarace s následujícím kódem. Tento kód má `ISheet1` veřejné rozhraní, a to se vztahuje <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut zpřístupněte rozhraní COM.  
  
     [!code-csharp[Trin_CallingCSCustomizationFromVBA#4](../vsto/codesnippet/CSharp/CallingCodeFromVBA/ISheet1.cs#4)]  
  
6.  Sestavte projekt.  
  
## <a name="expose-the-method-to-vba-code"></a>Vystavení metody VBA kód  
 Ke zveřejnění `CreateVstoNamedRange` Metoda VBA pro vytváření kódu v sešitu nastavena **ReferenceAssemblyFromVbaProject** vlastnost pro `Sheet1` hostitele položky **True**.  
  
### <a name="to-expose-the-method-to-vba-code"></a>Aby se zveřejnily metody VBA kód  
  
1.  V **Průzkumníku řešení**, dvakrát klikněte na **Sheet1.cs**.  
  
     **WorkbookWithVBA** soubor se otevře v Návrháři s Sheet1 viditelné.  
  
2.  V **vlastnosti** vyberte **ReferenceAssemblyFromVbaProject** vlastnost a změňte hodnotu na **True**.  
  
3.  Klikněte na tlačítko **OK** zprávy, která se zobrazí.  
  
4.  Sestavte projekt.  
  
## <a name="call-the-method-from-vba-code"></a>Volání metody z jazyka VBA kód  
 Nyní můžete volat `CreateVstoNamedRange` metoda z kódu jazyka VBA v sešitu.  
  
> [!NOTE]  
>  V tomto návodu přidáte VBA kód k sešitu při ladění projektu. VBA kód, které přidáte k tomuto dokumentu budou přepsány příštím sestavení projektu, protože Visual Studio nahradí kopii dokumentu ze složky hlavní projektu dokumentu do výstupní složky sestavení. Pokud chcete uložit VBA kód, zkopírujte jej do dokumentu ve složce projektu. Další informace najdete v tématu [kombinovat VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md).  
  
### <a name="to-call-the-method-from-vba-code"></a>K volání metody z jazyka VBA kód  
  
1.  Stiskněte klávesu **F5** ke spuštění projektu.  
  
2.  Na **vývojáře** ve **kód** klikněte na možnost **jazyka Visual Basic**.  
  
     Otevře se Editor jazyka Visual Basic.  
  
3.  Na **vložit** nabídky, klikněte na tlačítko **modulu**.  
  
4.  Přidejte následující kód do nového modulu.  
  
     Tento kód zavolá `CreateTable` metoda v sestavení vlastní nastavení. Makro používá tato metoda pomocí na globální `GetManagedClass` metody přístup `Sheet1` položky třída, která vystaveni VBA kód hostitele. `GetManagedClass` Metoda byl automaticky vygenerován při nastavení **ReferenceAssemblyFromVbaProject** vlastnost dříve v tomto návodu.  
  
    ```vb  
    Sub CallVSTOMethod()  
        Dim VSTOSheet1 As CallingCodeFromVBA.Sheet1  
        Set VSTOSheet1 = GetManagedClass(Sheet1)  
        Call VSTOSheet1.CreateVstoNamedRange(Sheet1.Range("A1"), "VstoNamedRange")  
    End Sub  
    ```  
  
5.  Stiskněte klávesu **F5**.  
  
6.  Do otevřeného sešitu, klikněte na buňku **A1** na **Sheet1**. Ověřte, že se zobrazí okno se zprávou.  
  
7.  Ukončete aplikaci Excel bez uložení změn.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o volání kódu v řešeních pro systém Office z jazyka VBA v těchto tématech:  
  
-   Volání kódu v hostitelská položka v přizpůsobením jazyka Visual Basic z jazyka VBA. Tento proces se liší od proces Visual C#. Další informace najdete v tématu [návod: volání kódu z jazyka VBA v projektu jazyka Visual Basic](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md).  
  
-   Volání kódu v doplňku VSTO z jazyka VBA. Další informace najdete v tématu [návod: volání kódu v doplňku VSTO z jazyka VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
## <a name="see-also"></a>Viz také:  
 [Kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md)   
 [Úpravy na úrovni dokumentů programu](../vsto/programming-document-level-customizations.md)   
 [Postupy: vystavení kódu do VBA v projektu jazyka Visual Basic](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md)   
 [Postupy: vystavení kódu do VBA v Visual C&#35; projektu](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)   
 [Návod: Volání kódu z jazyka VBA v projektu jazyka Visual Basic](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)  
  
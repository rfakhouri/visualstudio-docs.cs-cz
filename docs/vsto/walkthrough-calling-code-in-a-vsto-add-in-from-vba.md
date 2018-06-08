---
title: 'Návod: Volání kódu v doplňku VSTO z jazyka VBA'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VBA [Office development in Visual Studio], calling code in application-level add-ins
- application-level add-ins [Office development in Visual Studio], calling code from other solutions
- Video How tos, Office development in Visual Studio
- calling add-in code
- add-ins [Office development in Visual Studio], calling code from other solutions
- interoperability [Office development in Visual Studio]
- calling code from VBA
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1349facda26418907f039c80c7742d3c456437af
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845714"
---
# <a name="walkthrough-call-code-in-a-vsto-add-in-from-vba"></a>Návod: Volání kódu v doplňku VSTO z jazyka VBA
  Tento návod ukazuje, jak vystavit objekt VSTO Add-in do jiných řešení pro Microsoft Office, včetně Visual Basic for Applications (VBA) a doplňků COM VSTO.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 I když tento návod používá Excel konkrétně, koncepty ukázán podle návodu se vztahují na všechny doplňku VSTO šablona projektu poskytované sadě Visual Studio.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Definování třídu, která mohou být zpřístupněny na jiných řešení pro Office.  
  
-   Vystavení třídy pro jiných řešení pro Office.  
  
-   Volání metody třídy z jazyka VBA kód.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Excel  
  
## <a name="create-the-vsto-add-in-project"></a>Vytvoření projektu doplňku VSTO  
 Prvním krokem je vytvoření projektu doplňku VSTO pro Excel.  
  
### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu doplňku VSTO pro Excel s názvem **ExcelImportData**, pomocí šablony projektu doplňku VSTO v Excelu. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otevře se **ThisAddIn.cs** nebo **ThisAddIn.vb** kód soubor a přidá **ExcelImportData** projektu do **Průzkumníku řešení**.  
  
## <a name="define-a-class-that-you-can-expose-to-other-office-solutions"></a>Definice třídy, která můžete vystavit do jiných řešení pro systém Office  
 Účelem tohoto návodu je volání do `ImportData` metoda třídy s názvem `AddInUtilities` v doplňku VSTO z jazyka VBA kód. Tato metoda zapíše řetězec do buňky A1 aktivního listu.  
  
 Ke zveřejnění `AddInUtilities` třída chcete jiných řešení pro Office, musíte provést třída veřejné a viditelné v rámci modelu COM. Je nutné také zveřejnit [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) rozhraní ve třídě. Kód v následujícím postupu ukazuje jeden způsob, jak tyto požadavky splňují. Další informace najdete v tématu [volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
### <a name="to-define-a-class-that-you-can-expose-to-other-office-solutions"></a>Chcete-li definovat třídu, která můžete vystavit do jiných řešení pro Office  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat třídu**.  
  
2.  V **přidat novou položku** dialogové okno pole, změňte název nové třídy pro **AddInUtilities**a klikněte na tlačítko **přidat**.  
  
     **AddInUtilities.cs** nebo **AddInUtilities.vb** soubor se otevře v editoru kódu.  
  
3.  Na začátek souboru přidejte následující příkazy.  
  
     [!code-csharp[Trin_AddInInteropWalkthrough#2](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/AddInUtilities.cs#2)]
     [!code-vb[Trin_AddInInteropWalkthrough#2](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/AddInUtilities.vb#2)]  
  
4.  Nahraďte `AddInUtilities` třídy následujícím kódem.  
  
     [!code-csharp[Trin_AddInInteropWalkthrough#3](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/AddInUtilities.cs#3)]
     [!code-vb[Trin_AddInInteropWalkthrough#3](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/AddInUtilities.vb#3)]  
  
     Tento kód má `AddInUtilities` třídy viditelné do modelu COM, a přidá `ImportData` metodu do třídy. Ke zveřejnění [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) rozhraní, `AddInUtilities` třída má také <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atribut a implementuje rozhraní, které se zobrazí COM.  
  
## <a name="expose-the-class-to-other-office-solutions"></a>Vystavení třídy pro jiné řešení pro systém Office  
 Ke zveřejnění `AddInUtilities` třídy do jiných řešení pro Office, přepsat <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> metoda v `ThisAddIn` – třída. V přepsání, vrátit instanci `AddInUtilities` třídy.  
  
### <a name="to-expose-the-addinutilities-class-to-other-office-solutions"></a>Aby se zveřejnily třídy pro AddInUtilities jiných řešení pro systém Office  
  
1.  V **Průzkumníku řešení**, rozbalte položku **Excel**.  
  
2.  Klikněte pravým tlačítkem na **ThisAddIn.cs** nebo **ThisAddIn.vb**a potom klikněte na **kód zobrazení**.  
  
3.  Přidejte následující kód, který `ThisAddIn` třídy.  
  
     [!code-csharp[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/ThisAddIn.cs#1)]
     [!code-vb[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/ThisAddIn.vb#1)]  
  
4.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
     Ověřte, že sestavení řešení bez chyb.  
  
## <a name="test-the-vsto-add-in"></a>Testování doplňku VSTO  
 Můžete volat do `AddInUtilities` třídy z několika různých typů řešení pro systém Office. V tomto návodu použijete VBA kód v sešitu aplikace Excel. Další informace o ostatních typů řešení pro systém Office můžete také použít, najdete v části [volání kódu v doplňcích VSTO z jiných řešení pro Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
### <a name="to-test-your-vsto-add-in"></a>K testování vaší doplňku VSTO  
  
1.  Stiskněte klávesu **F5** ke spuštění projektu.  
  
2.  V aplikaci Excel uložte jako sešit aplikace Excel Macro-Enabled (XLSM) aktivním sešitu. Ho uložte do vhodného umístění, jako je například plochy.  
  
3.  Na pásu karet klikněte na **vývojáře** kartě.  
  
    > [!NOTE]  
    >  Pokud **vývojáře** karta není viditelný, musíte ji nejdříve zobrazit. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
4.  V **kód** klikněte na možnost **jazyka Visual Basic**.  
  
     Otevře se Editor jazyka Visual Basic.  
  
5.  V **projektu** okna, klikněte dvakrát na **ThisWorkbook**.  
  
     V souboru kódu `ThisWorkbook` objektu se otevře.  
  
6.  Přidejte následující VBA kód do souboru kódu. Tento kód získá nejprve COMAddIn objekt, který reprezentuje **ExcelImportData** doplňku VSTO. Potom kód používá objekt vlastnost objektu COMAddIn k volání `ImportData` metoda.  
  
    ```vb  
    Sub CallVSTOMethod()  
        Dim addIn As COMAddIn  
        Dim automationObject As Object  
        Set addIn = Application.COMAddIns("ExcelImportData")  
        Set automationObject = addIn.Object  
        automationObject.ImportData  
    End Sub  
    ```  
  
7.  Stiskněte klávesu **F5**.  
  
8.  Ověřte, že nový **importovat Data** list byl přidán do sešitu. Také ověřte, že buňky A1 obsahuje řetězec **jedná se o Moje data**.  
  
9. Ukončete aplikaci Excel.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o programování doplňků VSTO z těchto témat:  
  
-   Použití `ThisAddIn` třída automatizovat hostitelskou aplikaci a provádět další úlohy v projekty doplňku VSTO. Další informace najdete v tématu [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md).  
  
-   Vytvoření vlastního podokna úloh v doplňku VSTO. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md) a [postupy: Přidání vlastního podokna úloh do aplikace](../vsto/how-to-add-a-custom-task-pane-to-an-application.md).  
  
-   Přizpůsobení pásu karet v doplňku VSTO. Další informace najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md) a [postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
## <a name="see-also"></a>Viz také:  
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)   
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Přizpůsobení funkcí uživatelského rozhraní pomocí rozšiřujících rozhraní](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md)  
  
  
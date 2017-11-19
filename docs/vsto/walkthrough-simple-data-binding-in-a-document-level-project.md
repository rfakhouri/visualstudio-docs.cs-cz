---
title: "Návod: Jednoduché datové vazby v projektech na úrovni dokumentu | Microsoft Docs"
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
- data binding [Office development in Visual Studio], worksheet cell to Database field
- worksheets [Office development in Visual Studio], binding worksheet cell to Database field
- Database field [Office development in Visual Studio]
- data [Office development in Visual Studio], binding data
- simple data binding [Office development in Visual Studio]
ms.assetid: 6b8fd638-af13-4ea1-b1c0-2763e2d8ae23
caps.latest.revision: "58"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 847b547aae785d94f8d9025b7b4badf9d8b21075
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-simple-data-binding-in-a-document-level-project"></a>Návod: Jednoduché datové vazby v projektech na úrovni dokumentu
  Tento návod ukazuje základní informace o datové vazby v projektech na úrovni dokumentu. Jedno datové pole v databázi systému SQL Server je vázána na pojmenované oblasti v aplikaci Microsoft Office Excel. Průvodce také ukazuje, jak k přidávání ovládacích prvků, které umožňují procházet všechny záznamy v tabulce.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytváření zdroje dat pro projekt aplikace Excel.  
  
-   Přidání ovládacích prvků na list.  
  
-   Posouvání záznamů databáze.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Přístup na server s ukázková databáze Northwind SQL Server.  
  
-   Oprávnění ke čtení z a zapisovat do databáze SQL serveru.  
  
## <a name="creating-a-new-project"></a>Vytvoření nového projektu  
 V tomto kroku vytvoříte projekt sešitu aplikace Excel.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu sešitu aplikace Excel s názvem **Moje jednoduché datové vazby**, pomocí Visual Basic a C#. Ujistěte se, že **vytvoříte nový textový dokument** je vybrána. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Visual Studio otevře nové sešitu aplikace Excel v návrháři a přidá **Moje jednoduché datové vazby** projektu do **Průzkumníku řešení**.  
  
## <a name="creating-the-data-source"></a>Vytvoření zdroje dat  
 Použití **zdroje dat** okno pro přidání typové datové sady do projektu.  
  
#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat  
  
1.  Pokud **zdroje dat** okno není viditelný, zobrazit, na řádku nabídky, výběr **zobrazení**, **ostatní okna**, **zdroje dat**.  
  
2.  Zvolte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.  
  
3.  Vyberte **databáze** a pak klikněte na **Další**.  
  
4.  Vybrat datové připojení k systému SQL Server ukázková databáze Northwind, nebo přidat nové připojení pomocí **nové připojení** tlačítko.  
  
5.  Po připojení byla vybrána nebo vytvořili, klikněte na tlačítko **Další**.  
  
6.  Zrušte možnost uložit připojení, pokud je zaškrtnuto a pak klikněte na **Další**.  
  
7.  Rozbalte položku **tabulky** uzlu **databázové objekty** okno.  
  
8.  Zaškrtněte políčko vedle položky **zákazníci** tabulky.  
  
9. Klikněte na tlačítko **Dokončit**.  
  
 Průvodce přidá **zákazníci** a **zdroje dat** okno. Také přidá typové datové sady do projektu, který se zobrazí na **Průzkumníku řešení**.  
  
## <a name="adding-controls-to-the-worksheet"></a>Přidání ovládacích prvků na list  
 V tomto návodu budete potřebovat dva pojmenované oblasti a čtyři tlačítka na prvním listu. Nejprve přidejte dva pojmenované oblasti z **zdroje dat** okna tak, aby automaticky jsou vázány na zdroj dat. Dál přidejte tlačítka z **sada nástrojů**.  
  
#### <a name="to-add-two-named-ranges"></a>Chcete-li přidat dva pojmenované oblasti  
  
1.  Ověřte, zda **Moje jednoduché Binding.xlsx Data** je sešit otevřít v návrháři Visual Studio s **Sheet1** zobrazí.  
  
2.  Otevřete **zdroje dat** okno a rozbalte **zákazníci** uzlu.  
  
3.  Vyberte **NázevSpolečnosti** sloupce a potom klikněte na šipku rozevíracího seznamu, který se zobrazí.  
  
4.  Vyberte **NamedRange** v rozevíracím seznamu a pak přetáhněte **#companyname** sloupce do pole **A1**.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `companyNameNamedRange` je vytvořen v buňce **A1**. Ve stejnou dobu <xref:System.Windows.Forms.BindingSource> s názvem `customersBindingSource`, adaptérem tabulky a <xref:System.Data.DataSet> instance jsou přidány do projektu. Ovládací prvek vázán <xref:System.Windows.Forms.BindingSource>, který naopak je vázána <xref:System.Data.DataSet> instance.  
  
5.  Vyberte **CustomerID** sloupec v **zdroje dat** okno a potom klikněte na šipku rozevíracího seznamu, který se zobrazí.  
  
6.  Klikněte na tlačítko **NamedRange** v rozevíracím seznamu a pak přetáhněte **CustomerID** sloupce do pole **B1**.  
  
7.  Jiné <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `customerIDNamedRange` je vytvořen v buňce **B1**a vázaný k <xref:System.Windows.Forms.BindingSource>.  
  
#### <a name="to-add-four-buttons"></a>Chcete-li přidat čtyři tlačítka  
  
1.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přidejte <xref:System.Windows.Forms.Button> ovládacího prvku do buňky **A3** listu.  
  
     Toto tlačítko nazývalo `Button1`.  
  
2.  Tak, aby byly názvy, jak je znázorněno, přidejte tři další tlačítka na následující buňky v tomto pořadí:  
  
    |Buňky|(Název)|  
    |----------|--------------|  
    |B3|BUTTON2|  
    |C3|Button3|  
    |D3|Button4|  
  
 Dalším krokem je přidání textu do tlačítka a v jazyce C# přidejte obslužné rutiny událostí.  
  
## <a name="initializing-the-controls"></a>Inicializace ovládacích prvků  
 Nastavte text tlačítka a přidejte obslužné rutiny událostí během <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> událostí.  
  
#### <a name="to-initialize-the-controls"></a>K chybě při inicializaci ovládacích prvků  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Sheet1.vb** nebo **Sheet1.cs**a potom klikněte na **kód zobrazení** v místní nabídce.  
  
2.  Přidejte následující kód, který `Sheet1_Startup` metodu a nastavit text pro každé tlačítko.  
  
     [!code-csharp[Trin_VstcoreDataExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreDataExcel#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#2)]  
  
3.  Pro jazyk C# pouze, přidejte obslužné rutiny události pro tlačítko klikněte na události `Sheet1_Startup` metoda.  
  
     [!code-csharp[Trin_VstcoreDataExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#3)]  
  
 Teď přidejte kód pro zpracování <xref:System.Windows.Forms.Control.Click> události tlačítek tak, aby uživatel můžete procházet záznamy.  
  
## <a name="adding-code-to-enable-scrolling-through-the-records"></a>Přidání kódu povolit posouvání záznamů  
 Přidejte kód, který <xref:System.Windows.Forms.Control.Click> obslužné rutiny události z každé tlačítko pro procházení záznamů.  
  
#### <a name="to-move-to-the-first-record"></a>Pro přesun na první záznam  
  
1.  Přidání obslužné rutiny události pro <xref:System.Windows.Forms.Control.Click> události `Button1` tlačítko a přidejte následující kód pro přesun na první záznam:  
  
     [!code-csharp[Trin_VstcoreDataExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreDataExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#4)]  
  
#### <a name="to-move-to-the-previous-record"></a>Pro přesun do předchozího záznamu  
  
1.  Přidání obslužné rutiny události pro <xref:System.Windows.Forms.Control.Click> události `Button2` tlačítko a přidejte následující kód k přesunutí pozici zpět pomocí jedné:  
  
     [!code-csharp[Trin_VstcoreDataExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreDataExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#5)]  
  
#### <a name="to-move-to-the-next-record"></a>Pro přesun na další záznam  
  
1.  Přidání obslužné rutiny události pro <xref:System.Windows.Forms.Control.Click> události `Button3` tlačítko a přidejte následující kód posunut o jednu pozici:  
  
     [!code-csharp[Trin_VstcoreDataExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreDataExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#6)]  
  
#### <a name="to-move-to-the-last-record"></a>Chcete-li přesunout na poslední záznam  
  
1.  Přidání obslužné rutiny události pro <xref:System.Windows.Forms.Control.Click> události `Button4` tlačítko a přidejte následující kód k přesunutí na poslední záznam:  
  
     [!code-csharp[Trin_VstcoreDataExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreDataExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#7)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Nyní můžete otestovat vašeho sešitu, abyste měli jistotu, že můžete procházet záznamy v databázi.  
  
#### <a name="to-test-your-workbook"></a>K testování sešitu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Potvrdit, že na první záznam zobrazí v buňkách **A1** a **B1**.  
  
3.  Klikněte  **>**  (`Button3`) tlačítko a potvrďte, že se zobrazí na další záznam v buňce **A1** a **B1**.  
  
4.  Klikněte na tlačítko Další tlačítka posuvníku potvrďte, že záznam se změní podle očekávání.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základní informace o vytvoření vazby pojmenované oblasti na pole v databázi. Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Data v mezipaměti, aby se může použít do offline režimu. Další informace najdete v tématu [postup: Data do mezipaměti pro použití v režimu Offline nebo na serveru](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   Vytvoření vazby buňky do více sloupců v tabulce, místo s jedno pole. Další informace najdete v tématu [návod: komplexní datové vazby v projektech na úrovni dokumentu](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md).  
  
-   Použití <xref:System.Windows.Forms.BindingNavigator> řízení procházet záznamů. Další informace najdete v tématu [postup: přejděte dat pomocí ovládacího prvku Windows Forms BindingNavigator](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms).  
  
## <a name="see-also"></a>Viz také  
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)   
 [Návod: Rozšířené datové vazby v projektech na úrovni dokumentu](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)  
  
  
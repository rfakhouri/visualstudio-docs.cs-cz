---
title: "Návod: Vytvoření hlavního podrobný vztah, který pomocí datové sady v mezipaměti | Microsoft Docs"
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
- master-detail tables [Office development in Visual Studio], walkthroughs
- data caching [Office development in Visual Studio], Master/Detail Relation
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 161fdc5e35a24b1318a44d2102867961330ba559
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-a-master-detail-relation-using-a-cached-dataset"></a>Návod: Vytvoření hlavního podrobný vztah, který pomocí datové sady v mezipaměti
  Tento návod ukazuje vytvoření vztahu seznam podrobnosti v listu a ukládání do mezipaměti dat, aby řešení můžete použít v režimu offline.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Během tohoto návodu se dozvíte, jak:  
  
-   Přidání ovládacích prvků na list.  
  
-   Nastavení datové sady do mezipaměti v listu.  
  
-   Přidáte kód pro povolení přecházení mezi záznamy.  
  
-   Testování projektu.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Přístup k ukázkové databázi Northwind SQL Server. Databáze může být na vašem vývojovém počítači nebo na serveru.  
  
-   Oprávnění ke čtení z a zapisovat do databáze SQL serveru.  
  
## <a name="creating-a-new-project"></a>Vytvoření nového projektu  
 V tomto kroku vytvoříte projekt sešitu aplikace Excel.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu sešitu aplikace Excel s názvem **Moje seznam-podrobnosti**, pomocí Visual Basic a C#. Ujistěte se, že **vytvoříte nový textový dokument** je vybrána. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Visual Studio otevře nové sešitu aplikace Excel v návrháři a přidá **Moje seznam-podrobnosti** projektu do **Průzkumníku řešení**.  
  
## <a name="creating-the-data-source"></a>Vytvoření zdroje dat  
 Použití **zdroje dat** okno pro přidání typové datové sady do projektu.  
  
#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat  
  
1.  Pokud **zdroje dat** okno není viditelný, zobrazit, na řádku nabídky, výběr **zobrazení**, **ostatní okna**, **zdroje dat**.  
  
2.  Zvolte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.  
  
3.  Vyberte **databáze** a pak klikněte na **Další**.  
  
4.  Vyberte datové připojení k systému SQL Server ukázková databáze Northwind, nebo přidejte nové připojení pomocí **nové připojení** tlačítko.  
  
5.  Po výběru nebo vytvoření připojení, klikněte na tlačítko **Další**.  
  
6.  Zrušte možnost uložit připojení, pokud je zaškrtnuto a pak klikněte na **Další**.  
  
7.  Rozbalte položku **tabulky** uzlu **databázové objekty** okno.  
  
8.  Vyberte **objednávky** tabulky a **pořadí podrobnosti** tabulky.  
  
9. Klikněte na tlačítko **Dokončit**.  
  
 Průvodce přidá dvě tabulky **zdroje dat** okno. Také přidá typové datové sady do projektu, který se zobrazí na **Průzkumníku řešení**.  
  
## <a name="adding-controls-to-the-worksheet"></a>Přidání ovládacích prvků na list  
 V tomto kroku přidáte pojmenované oblasti, objekt seznamu a dvě tlačítka první sešitu. Nejprve přidejte pojmenované oblasti a objekt v seznamu **zdroje dat** okna tak, aby automaticky jsou vázány na zdroj dat. Dál přidejte tlačítka z **sada nástrojů**.  
  
#### <a name="to-add-a-named-range-and-a-list-object"></a>Chcete-li přidat pojmenované oblasti a objekt seznamu  
  
1.  Ověřte, zda **Moje hlavní-Detail.xlsx** je sešit otevřít v návrháři Visual Studio s **Sheet1** zobrazí.  
  
2.  Otevřete **zdroje dat** okno a rozbalte **objednávky** uzlu.  
  
3.  Vyberte **OrderID** sloupce a potom klikněte na šipku rozevíracího seznamu, který se zobrazí.  
  
4.  Klikněte na tlačítko **NamedRange** v rozevíracím seznamu a pak přetáhněte **OrderID** sloupce do pole **A2**.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `OrderIDNamedRange` je vytvořen v buňce **A2**. Ve stejnou dobu <xref:System.Windows.Forms.BindingSource> s názvem `OrdersBindingSource`, adaptérem tabulky a <xref:System.Data.DataSet> instance jsou přidány do projektu. Ovládací prvek vázán <xref:System.Windows.Forms.BindingSource>, který naopak je vázána <xref:System.Data.DataSet> instance.  
  
5.  Posuňte se dolů po sloupce, které jsou v části **objednávky** tabulky. V dolní části seznamu je **pořadí podrobnosti** tabulky; je zde, protože je podřízená **objednávky** tabulky. Tuto možnost vyberte, **pořadí podrobnosti** tabulky, není ten, který je na stejné úrovni jako **objednávky** tabulky a potom klikněte na šipku rozevíracího seznamu, který se zobrazí.  
  
6.  Klikněte na tlačítko **ListObject** v rozevíracím seznamu a pak přetáhněte **Rozpis objednávek** tabulky do buňky **A6**.  
  
7.  A <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek s názvem **Order_DetailsListObject** je vytvořen v buňce **A6**a vázaný k <xref:System.Windows.Forms.BindingSource>.  
  
#### <a name="to-add-two-buttons"></a>Chcete-li přidat dvě tlačítka  
  
1.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přidejte <xref:System.Windows.Forms.Button> ovládacího prvku do buňky **A3** listu.  
  
     Toto tlačítko nazývalo `Button1`.  
  
2.  Přidejte další <xref:System.Windows.Forms.Button> ovládacího prvku do buňky **B3** listu.  
  
     Toto tlačítko nazývalo `Button2`.  
  
 V dalším kroku označte datové sady do mezipaměti v dokumentu.  
  
## <a name="caching-the-dataset"></a>Ukládání do mezipaměti datové sady  
 Označit datové sady do mezipaměti v dokumentu tím, že datová sada veřejné a nastavení **CacheInDocument** vlastnost.  
  
#### <a name="to-cache-the-dataset"></a>Pro ukládání do mezipaměti datové sady  
  
1.  Vyberte **NorthwindDataSet** na hlavním panelu součásti.  
  
2.  V **vlastnosti** změňte **modifikátory** vlastnost **veřejné**.  
  
     Předtím, než je povoleno ukládání do mezipaměti, musí být veřejné datové sady.  
  
3.  Změna **CacheInDocument** vlastnost **True**.  
  
 Dalším krokem je přidání textu do tlačítka a v jazyce C# přidejte kód spojit Obslužné rutiny událostí.  
  
## <a name="initializing-the-controls"></a>Inicializace ovládacích prvků  
 Nastavte text tlačítka a přidejte obslužné rutiny událostí během <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> událostí.  
  
#### <a name="to-initialize-the-data-and-the-controls"></a>K chybě při inicializaci dat a ovládací prvky  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Sheet1.vb** nebo **Sheet1.cs**a potom klikněte na **kód zobrazení** v místní nabídce.  
  
2.  Přidejte následující kód, který `Sheet1_Startup` metodu a nastavit text pro tlačítka.  
  
     [!code-vb[Trin_VstcoreDataExcel#15](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet2.vb#15)]
     [!code-csharp[Trin_VstcoreDataExcel#15](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#15)]  
  
3.  Pro jazyk C# pouze, přidejte obslužné rutiny události pro tlačítko klikněte na události `Sheet1_Startup` metoda.  
  
     [!code-csharp[Trin_VstcoreDataExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#16)]  
  
## <a name="adding-code-to-enable-scrolling-through-the-records"></a>Přidání kódu povolit posouvání záznamů  
 Přidejte kód, který <xref:System.Windows.Forms.Control.Click> obslužné rutiny události z každé tlačítko pro procházení záznamů.  
  
#### <a name="to-scroll-through-the-records"></a>Chcete-li procházet záznamů  
  
1.  Přidání obslužné rutiny události pro <xref:System.Windows.Forms.Control.Click> události `Button1`a přidejte následující kód do zpětné procházení záznamů:  
  
     [!code-vb[Trin_VstcoreDataExcel#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet2.vb#17)]
     [!code-csharp[Trin_VstcoreDataExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#17)]  
  
2.  Přidání obslužné rutiny události pro <xref:System.Windows.Forms.Control.Click> události `Button2`a přidejte následující kód do zálohy prostřednictvím záznamy:  
  
     [!code-vb[Trin_VstcoreDataExcel#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet2.vb#18)]
     [!code-csharp[Trin_VstcoreDataExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#18)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Nyní můžete otestovat vašeho sešitu, abyste měli jistotu, že data zobrazuje podle očekávání a, které můžete použít řešení do offline režimu.  
  
#### <a name="to-test-the-data-caching"></a>K otestování dat ukládání do mezipaměti  
  
1.  Stiskněte klávesu **F5**.  
  
2.  Ověřte, že pojmenované oblasti a objekt seznamu jsou vyplněny dat ze zdroje dat.  
  
3.  Posuňte některé záznamy klepnutím na tlačítka.  
  
4.  Sešit uložte a zavřete sešit a Visual Studio.  
  
5.  Zakážete připojení k databázi. Odpojte síťový kabel z vašeho počítače, pokud se databáze nachází na serveru, nebo zastavte službu serveru SQL Server, pokud se databáze nachází na vašem vývojovém počítači.  
  
6.  Otevřete aplikaci Excel a pak otevřete **Moje hlavní-Detail.xlsx** z adresáře \bin (\My Master-Detail\bin v jazyce Visual Basic nebo \My Master-Detail\bin\debug v jazyce C#).  
  
7.  Posuňte některé záznamy zobrazit, že listu pracuje normálně při odpojení.  
  
8.  Znovu se připojte k databázi. Připojení počítače k síti znovu Pokud se databáze nachází na serveru, nebo spusťte službu SQL Server, pokud se databáze nachází na vašem vývojovém počítači.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základní informace o vytvoření vztahu seznam podrobnosti dat v listu a ukládání do mezipaměti datové sady. Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Nasazení řešení. Další informace najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
## <a name="see-also"></a>Viz také  
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)   
 [Ukládání dat do mezipaměti](../vsto/caching-data.md)   
 [Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)  
  
  
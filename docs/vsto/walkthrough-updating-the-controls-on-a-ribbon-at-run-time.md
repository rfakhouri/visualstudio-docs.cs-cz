---
title: "Návod: Aktualizace ovládacích prvků na pásu karet za běhu | Microsoft Docs"
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
- controls [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], controls
- updating Ribbon controls
- Ribbon [Office development in Visual Studio], dynamic menu
- dynamic menus [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], updating
ms.assetid: ed80790f-3f95-47e4-8a41-872588a8ca07
caps.latest.revision: "51"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bf9e63423a094d4aa574be1d952702ff077aa627
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-updating-the-controls-on-a-ribbon-at-run-time"></a>Návod: Aktualizace ovládacích prvků na pásu karet za běhu
  Tento návod ukazuje, jak aktualizovat ovládacích prvků na pásu karet po načtení pásu karet do aplikace Office pomocí modelu objektů pásu karet.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 V příkladu získává data ze ukázková databáze Northwind k vyplnění pole se seznamem a nabídky v aplikaci Microsoft Office Outlook. Položky, které jste vybrali v těchto ovládacích prvků automaticky naplnění polí, jako **k** a **subjektu** e-mailové zprávy.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření nového projektu doplňku VSTO v Outlooku.  
  
-   Návrh vlastní skupiny pásu karet.  
  
-   Přidávání vlastní skupiny k předdefinované karty.  
  
-   Aktualizace ovládacích prvků na pásu karet za běhu.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Outlook  
  
## <a name="creating-a-new-outlook-vsto-add-in-project"></a>Vytvoření nové aplikace Outlook VSTO přidejte v projektu  
 Nejprve vytvořte projektu doplňku VSTO v Outlooku.  
  
#### <a name="to-create-a-new-outlook-vsto-add-in-project"></a>K vytvoření nového projektu doplňku VSTO pro Outlook  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vytvoření projektu doplňku VSTO pro Outlook s názvem **Ribbon_Update_At_Runtime**.  
  
2.  V **nový projekt** dialogové okno, vyberte **vytvořit adresář pro řešení**.  
  
3.  Uložte projekt do výchozí adresář projektu.  
  
     Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
## <a name="designing-a-custom-ribbon-group"></a>Návrh vlastní skupiny pásu karet  
 Na pásu karet v tomto příkladu se zobrazí, když uživatel vytvoří novou e-mailovou zprávu. Pokud chcete vytvořit vlastní skupinu pro pás karet, nejprve přidat položku pásu karet do projektu a pak Navrhněte skupiny v Návrháři pásu karet. Tato vlastní skupiny vám pomůže generovat následné e-mailových zpráv pro zákazníky přidáváním názvy a pořadí historií z databáze.  
  
#### <a name="to-design-a-custom-group"></a>Při návrhu vlastní skupiny  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **pásu karet (vizuálního návrháře)**.  
  
3.  Změňte název nové pásu karet na **CustomerRibbon**a potom klikněte na **přidat**.  
  
     **CustomerRibbon.cs** nebo **CustomerRibbon.vb** soubor se otevře v Návrháři pásu karet a zobrazí se výchozí kartě a skupiny.  
  
4.  Klikněte na tlačítko Návrháře pásu karet vyberte.  
  
5.  V **vlastnosti** okně klikněte na šipku rozevíracího seznamu vedle položky **RibbonType** vlastnost a potom klikněte na **Microsoft.Outlook.Mail.Compose**.  
  
     To umožňuje na pásu karet se objeví, když uživatel vytvoří novou e-mailovou zprávu v Outlooku.  
  
6.  V Návrháři pásu karet klikněte na tlačítko **Group1** ji vyberte.  
  
7.  V **vlastnosti** nastavte **popisek** k **nákupy zákazníka**.  
  
8.  Z **ovládacích prvků pásu karet Office** kartě **sada nástrojů**, přetáhněte **ComboBox** na **nákupy zákazníka** skupiny.  
  
9. Klikněte na tlačítko **ComboBox1** ji vyberte.  
  
10. V **vlastnosti** nastavte **popisek** k **zákazníci**.  
  
11. Z **ovládacích prvků pásu karet Office** kartě **sada nástrojů**, přetáhněte **nabídky** na **nákupy zákazníka** skupiny.  
  
12. V **vlastnosti** nastavte **popisek** k **zakoupených produktů**.  
  
13. Nastavit **dynamické** k **true**.  
  
     To umožňuje přidávat a odebírat ovládací prvky v nabídce v době běhu po načtení pásu karet do aplikací Office.  
  
## <a name="adding-the-custom-group-to-a-built-in-tab"></a>Přidání vlastní skupiny do předdefinované karty  
 Předdefinované karta je karta, která je již na pásu karet Outlook Explorer nebo Inspector. V tomto postupu přidejte vlastní skupinu do předdefinované karty a pak zadejte na kartě pozice vlastní skupiny.  
  
#### <a name="to-add-the-custom-group-to-a-built-in-tab"></a>Chcete-li přidat vlastní skupinu pro předdefinované karty  
  
1.  Klikněte **TabAddins (předdefinovaná)** a vyberte ho.  
  
2.  V **vlastnosti** okno, rozbalte **ControlId** vlastnost a potom nastavte **OfficeId** k **TabNewMailMessage**.  
  
     Tím se přidá **nákupy zákazníka** skupiny k **zprávy** karty na pásu karet, které se zobrazí v nové e-mailovou zprávu.  
  
3.  Klikněte na tlačítko **nákupy zákazníka** skupina a vyberte ji.  
  
4.  V **vlastnosti** okno, rozbalte **pozice** vlastnosti, klikněte na šipku rozevíracího seznamu vedle položky **PositionType** vlastnost a potom klikněte na  **BeforeOfficeId**.  
  
5.  Nastavte **OfficeId** vlastnost **GroupClipboard**.  
  
     To umisťuje **nákupy zákazníka** skupiny před **schránky** u **zprávy** kartě.  
  
## <a name="creating-the-data-source"></a>Vytvoření zdroje dat  
 Použití **zdroje dat** okno pro přidání typové datové sady do projektu.  
  
#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat  
  
1.  Na **Data** nabídky, klikněte na tlačítko **přidat nový zdroj dat**.  
  
     Tím se spustí **Průvodce konfigurací zdroje dat**.  
  
2.  Vyberte **databáze**a potom klikněte na **Další**.  
  
3.  Vyberte **datovou sadu**a potom klikněte na **Další**.  
  
4.  Vyberte datové připojení k serveru Microsoft SQL Server Compact 4.0 ukázková databáze Northwind, nebo přidejte nové připojení pomocí **nové připojení** tlačítko.  
  
5.  Po připojení byla vybrána nebo vytvořili, klikněte na tlačítko **Další**.  
  
6.  Klikněte na tlačítko **Další** uložit připojovací řetězec.  
  
7.  Na **zvolte si databázové objekty** rozbalte **tabulky**.  
  
8.  Zaškrtněte políčko vedle každého z následujících tabulek:  
  
    1.  **Zákazníci**  
  
    2.  **Podrobnosti o objednávce**  
  
    3.  **Objednávky**  
  
    4.  **Produkty**  
  
9. Klikněte na tlačítko **Dokončit**.  
  
## <a name="updating-controls-in-the-custom-group-at-run-time"></a>Aktualizace ovládacích prvků ve skupině vlastní za běhu  
 Pomocí modelu objektů pásu karet provádět následující úlohy:  
  
-   Přidat názvy zákazníka **zákazníci** pole se seznamem.  
  
-   Přidání ovládacích prvků do nabídky a tlačítko **zakoupených produktů** prodaných nabídky, která představují prodeje objednávek a produkty.  
  
-   Naplnění na, předmět a text pole nové e-mailových zpráv pomocí dat z **zákazníci** – pole se seznamem a **zakoupených produktů** nabídky.  
  
#### <a name="to-update-controls-in-the-custom-group-by-using-the-ribbon-object-model"></a>Aktualizace ovládacích prvků v vlastní skupiny pomocí objektového modelu pásu karet  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat odkaz na**.  
  
2.  V **přidat odkaz na** dialogové okno, klikněte na tlačítko **.NET** vyberte **System.Data.Linq** sestavení a pak klikněte na tlačítko **OK**.  
  
     Toto sestavení obsahuje třídy pro používání Language-Integrated dotazy (LINQ). K naplnění ovládacích prvků v vlastní skupiny s daty z databáze Northwind použijete LINQ.  
  
3.  V **Průzkumníku řešení**, klikněte na tlačítko **CustomerRibbon.cs** nebo **CustomerRibbon.vb** ji vyberte.  
  
4.  Na **zobrazení** nabídky, klikněte na tlačítko **kód**.  
  
     Pás karet kód soubor se otevře v editoru kódu.  
  
5.  Přidejte následující příkazy na začátek souboru kódu pásu karet. Tyto příkazy poskytování snadného přístupu k LINQ obory názvů a obor názvů primární spolupracující sestavení aplikace Outlook (PIA).  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#1](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#1)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#1](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#1)]  
  
6.  Přidejte následující kód do třídy CustomerRibbon. Tento kód deklaruje tabulku dat a adaptéry tabulek, které budete používat k ukládání informací od zákazníků, objednávky, podrobnosti o pořadí a tabulek produktu databáze Northwind.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#2](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#2)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#2](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#2)]  
  
7.  Přidejte následující blok kódu `CustomerRibbon` třídy. Tento kód přidá tři pomocné metody, které vytvořit ovládací prvky pro pás karet za běhu.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#3](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#3)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#3](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#3)]  
  
8.  Nahraďte `CustomerRibbon_Load` metoda obslužné rutiny události s následujícím kódem. Tento kód používá dotaz LINQ k provádění následujících úloh:  
  
    -   Naplnění **zákazníci** pole se seznamem pomocí ID a název 20 zákazníků v databázi Northwind.  
  
    -   Volání `PopulateSalesOrderInfo` metodu helper. Tato metoda aktualizace **ProductsPurchased** nabídku prodeje pořadová čísla, které se týkají aktuálně vybraného zákazníka.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#4](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#4)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#4](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#4)]  
  
9. Přidejte následující kód, který `CustomerRibbon` třídy. Tento kód používá dotazů LINQ k provádění následujících úloh:  
  
    -   Přidá podnabídky k **ProductsPurchased** nabídky pro každou prodejní objednávku související s vybraného zákazníka.  
  
    -   Přidá tlačítka do každé podnabídky pro produkty týkající se prodeje pořadí.  
  
    -   Přidá obslužné rutiny událostí do každé tlačítko.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#6](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#6)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#6](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#6)]  
  
10. V **Průzkumníku**, poklikejte na soubor kódu pásu karet.  
  
     Otevře se Návrháře pásu karet.  
  
11. V Návrháři pásu karet klikněte dvakrát na **zákazníci** pole se seznamem.  
  
     Otevření souboru kódu pásu karet v editoru kódu a `ComboBox1_TextChanged` obslužné rutiny události se zobrazí.  
  
12. Nahraďte `ComboBox1_TextChanged` obslužné rutiny události s následujícím kódem. Tento kód provede následující:  
  
    -   Volání `PopulateSalesOrderInfo` metodu helper. Tato metoda aktualizace **zakoupených produktů** nabídku prodeje objednávek, které se týkají vybraného zákazníka.  
  
    -   Volání `PopulateMailItem` Pomocná metoda a předává v aktuální textu, což je název vybraného zákazníka. Tato metoda naplní na, předmět a text pole nové e-mailových zpráv.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#5](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#5)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#5](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#5)]  
  
13. Přidejte následující klikněte na obslužnou rutinu události `CustomerRibbon` – třída. Tento kód přidá název vybrané produkty do pole text novou e-mailových zpráv.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#8](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#8)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#8](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#8)]  
  
14. Přidejte následující kód, který `CustomerRibbon` třídy. Tento kód provede následující:  
  
    -   Naplní na řádku nové zprávy e-mailu pomocí e-mailovou adresu aktuálně vybraného zákazníka.  
  
    -   Přidá text do pole Předmět a text na nové e-mailových zpráv.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#7](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#7)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#7](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#7)]  
  
## <a name="testing-the-controls-in-the-custom-group"></a>Testování ve skupině pro vlastní ovládací prvky  
 Při otevření nového e-mailu formuláře v aplikaci Outlook, vlastní skupinu s názvem **nákupy zákazníka** se zobrazí na **zprávy** karty na pásu karet.  
  
 K vytvoření zákazníka následné e-mailové zprávy, vyberte zákazníka a pak vyberte produkty zakoupené zákazníka. Ovládací prvky v **nákupy zákazníka** skupiny jsou aktualizovány v době běhu pomocí dat z databáze Northwind.  
  
#### <a name="to-test-the-controls-in-the-custom-group"></a>K testování ve skupině pro vlastní ovládací prvky  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
     Spuštění aplikace Outlook.  
  
2.  V aplikaci Outlook na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **e-mailovou zprávu**.  
  
     Provedou se tyto akce:  
  
    -   Zobrazí se nové okno Inspector zprávy e-mailu.  
  
    -   Na **zpráva** karty na pásu karet **nákupy zákazníka** skupiny se zobrazuje před **schránky** skupiny.  
  
    -   **Zákazníci** s názvy zákazníků v databázi Northwind se aktualizuje pole se seznamem ve skupině.  
  
3.  Na **zpráva** karty na pásu karet v **nákupy zákazníka** skupiny, vyberte zákazníka z **zákazníci** pole se seznamem.  
  
     Provedou se tyto akce:  
  
    -   **Zakoupených produktů** nabídky aktualizována na každou prodejní objednávku pro vybraného zákazníka.  
  
    -   Každé podnabídky prodeje pořadí je aktualizována na tyto produkty zakoupili v tomto pořadí.  
  
    -   Vybrané zákazníka e-mailová adresa se přidá do **k** řádek e-mailovou zprávu a předmět a text e-mailovou zprávu se naplní text.  
  
4.  Klikněte **produkty nákupy** nabídky, přejděte na libovolném prodeje pořadí a klikněte na produkt z prodejní objednávky.  
  
     Název produktu je přidat k tělu e-mailovou zprávu.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak přizpůsobit rozhraní Office z těchto témat:  
  
-   Přidáte na základě kontextu uživatelského rozhraní pro přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [přehled podokna akcí](../vsto/actions-pane-overview.md).  
  
-   Rozšiřte standardními nebo vlastními formuláře aplikace Microsoft Office Outlook. Další informace najdete v tématu [návod: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md).  
  
-   Přidání vlastního podokna úloh do aplikace Outlook. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
## <a name="see-also"></a>Viz také  
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Language-Integrated Query (LINQ)](/dotnet/csharp/linq/index)   
 [Postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md)   
 [Přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Postupy: Změna polohy karty na pásu karet](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)   
 [Postupy: Přidání ovládacích prvků do zobrazení Backstage](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Postupy: Export pásu karet z Návrháře pásu karet do kódu XML pásu karet](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Postupy: Zobrazit chyby doplňku uživatelského rozhraní](../vsto/how-to-show-add-in-user-interface-errors.md)  
  
  
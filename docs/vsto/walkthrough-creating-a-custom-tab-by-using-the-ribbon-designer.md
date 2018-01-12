---
title: "Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet | Microsoft Docs"
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
- actions panes [Office development in Visual Studio], controlling from Ribbon
- Ribbon [Office development in Visual Studio], customizing
- Ribbon Designer [Office development in Visual Studio]
- customizing the Ribbon, tabs
- custom Ribbon, tabs
- Custom tab [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: cdbbd7ee286c97a986e89ccdb5bdcfdde4ef7578
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer"></a>Návod: Vytvoření vlastní karty pomocí návrháře pásu karet
  Pomocí Návrháře pásu karet, můžete vytvořit vlastní karty a pak přidejte a umisťování ovládacích prvků na něm.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   [Vytváření podokna akcí](#BKMK_CreateActionsPanes).  
  
-   [Vytvoření vlastní karty](#BKMK_CreateCustomTab).  
  
-   [Skrytí a zobrazení podokna akcí pomocí tlačítka na vlastní kartě](#BKMK_HideShowActionsPane).  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Excel  
  
## <a name="creating-an-excel-workbook-project"></a>Vytvoření projektu sešitu aplikace Excel  
 Postup pro používání návrháře pásu karet je skoro stejná pro všechny aplikace Office. Tento příklad používá sešitu aplikace Excel.  
  
#### <a name="to-create-an-excel-workbook-project"></a>Vytvoření projektu sešitu aplikace Excel  
  
-   Vytvoření projektu sešitu aplikace Excel s názvem **MyExcelRibbon**. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře do nového sešitu v návrháři a přidá **MyExcelRibbon** projektu do **Průzkumníku řešení**.  
  
##  <a name="BKMK_CreateActionsPanes"></a>Vytváření podokna akcí  
 Do projektu přidejte dvě podokna vlastní akce. Později přidáte tlačítek, zobrazení a skrytí podokna těchto akcí na vlastní kartě.  
  
#### <a name="to-create-actions-panes"></a>Chcete-li vytvořit podokna akcí  
  
1.  Na **projektu** nabídce zvolte **přidat novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **ActionsPaneControl**a potom zvolte **přidat**.  
  
     **ActionsPaneControl1.cs** nebo **ActionsPaneControl1.vb** soubor se otevře v návrháři.  
  
3.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přidejte popisek na plochu návrháře.  
  
4.  V **vlastnosti** nastavte **Text** vlastnost Label1 k **1 podokna akce**.  
  
5.  Opakujte kroky 1 až 5 vytvořte druhý podokna akce a popisku. Nastavte **Text** vlastnost druhý štítek, který chcete **2 podokna akce**.  
  
##  <a name="BKMK_CreateCustomTab"></a>Vytvoření vlastní karty  
 Jedním z pokynů pro návrh aplikace Office je, že uživatelé by měli mít vždy řízení aplikace Office uživatelského rozhraní. Pokud chcete přidat tuto možnost u podokna akcí, můžete přidat tlačítek, zobrazení a skrytí podokna každé akce z vlastní karty na pásu karet. Chcete-li vytvořit vlastní karty, přidejte **pásu karet (vizuálního návrháře)** položku do projektu. Návrháře umožňuje přidat a umístěte ovládací prvky, nastavení vlastností ovládacího prvku a zpracování události ovládacího prvku.  
  
#### <a name="to-create-a-custom-tab"></a>K vytvoření vlastní karty  
  
1.  Na **projektu** nabídce zvolte **přidat novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **pásu karet (vizuálního návrháře)**.  
  
3.  Změňte název nové pásu karet na **MyRibbon**a zvolte **přidat**.  
  
     **MyRibbon.cs** nebo **MyRibbon.vb** soubor se otevře v Návrháři pásu karet a zobrazí se výchozí kartě a skupiny.  
  
4.  V Návrháři pásu karet zvolte výchozí kartě.  
  
5.  V **vlastnosti** okno, rozbalte **ControlId** vlastnost a potom nastavte **ControlIdType** vlastnost **vlastní**.  
  
6.  Nastavte **popisek** vlastnost **Moje kartu Vlastní**.  
  
7.  V Návrháři pásu karet zvolte **group1**.  
  
8.  V **vlastnosti** nastavte **popisek** k **Manager podokna akce**.  
  
9. Z **ovládacích prvků pásu karet Office** kartě **sada nástrojů**, přetáhněte tlačítko na **group1**.  
  
10. Vyberte **button1**.  
  
11. V **vlastnosti** nastavte **popisek** k **zobrazit 1 podokna akce**.  
  
12. Přidání druhého tlačítka pro **group1**a nastavte **popisek** vlastnost **zobrazit 2 podokna akce**.  
  
13. Z **ovládacích prvků pásu karet Office** kartě **sada nástrojů**, přetáhněte ji **přepínací tlačítko** na ovládací prvek **group1**.  
  
14. Nastavte **popisek** vlastnost **skrytí podokna akce**.  
  
##  <a name="BKMK_HideShowActionsPane"></a>Skrytí a pomocí tlačítka na kartě Vlastní zobrazení podokna akcí  
 Posledním krokem je přidání kódu, který reaguje na uživatele. Přidání obslužných rutin událostí pro <xref:Microsoft.Office.Tools.Ribbon.RibbonButton.Click> události pro dvě tlačítka a <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> událostí přepínací tlačítko. Přidávání kódu do těchto obslužných rutin událostí Povolit skrytí a zobrazení podokna akcí.  
  
#### <a name="to-hide-and-show-actions-panes-by-using-buttons-in-the-custom-tab"></a>Skrýt a zobrazit pomocí tlačítka na vlastní kartě podokna akcí  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro MyRibbon.cs nebo MyRibbon.vb a potom zvolte **kód zobrazení**.  
  
2.  Přidejte následující kód do horní části `MyRibbon` třídy. Tento kód vytvoří dva objekty podokna akce.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab/MyRibbon.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab/MyRibbon.vb#1)]  
  
3.  Nahraďte `MyRibbon_Load` metoda následujícím kódem. Tento kód přidá objekty podokna akce, které se <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> kolekce a skryje objekty ze zobrazení. Kód jazyka Visual C# také připojí delegátů k několika události ovládacích prvků pásu karet.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab#2](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab/MyRibbon.cs#2)]
     [!code-vb[Trin_Ribbon_Custom_Tab#2](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab/MyRibbon.vb#2)]  
  
4.  Přidejte následující metody obslužná rutina tři události, které `MyRibbon` třídy. Tyto metody zpracování <xref:Microsoft.Office.Tools.Ribbon.RibbonButton.Click> události pro dvě tlačítka a <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> událostí přepínací tlačítko. Obslužné rutiny události pro button1 a button2 zobrazit podokna alternativní akcí. Obslužné rutiny události pro toggleButton1 zobrazí a skryje v podokně Akce active.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab#3](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab/MyRibbon.cs#3)]
     [!code-vb[Trin_Ribbon_Custom_Tab#3](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab/MyRibbon.vb#3)]  
  
## <a name="testing-the-custom-tab"></a>Testování na vlastní kartě  
 Při spuštění projektu, se spustí aplikace Excel a **Moje kartu Vlastní** karta se zobrazí na pásu karet. Zvolit tlačítka na **Moje kartu Vlastní** zobrazení a skrytí podokna akcí.  
  
#### <a name="to-test-the-custom-tab"></a>K testování na vlastní kartě  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Vyberte **Moje kartu Vlastní** kartě.  
  
3.  V **vlastní akce podokně Správce** skupiny, vyberte **zobrazit 1 podokna akce**.  
  
     Zobrazí se v podokně Akce a zobrazí popisek **1 podokna akce**.  
  
4.  Zvolte **zobrazit podokno akcí 2**.  
  
     Zobrazí se v podokně Akce a zobrazí popisek **2 podokna akce**.  
  
5.  Zvolte **skrytí podokna akce**.  
  
     Podokna akcí již nejsou viditelné.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak přizpůsobit rozhraní Office z těchto témat:  
  
-   Přidáte na základě kontextu uživatelského rozhraní pro přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [přehled podokna akcí](../vsto/actions-pane-overview.md).  
  
-   Rozšiřte standardními nebo vlastními formuláře aplikace Microsoft Office Outlook. Další informace najdete v tématu [návod: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md).  
  
## <a name="see-also"></a>Viz také  
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Postupy: Změna polohy karty na pásu karet](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)   
 [Postupy: Přidání ovládacích prvků do zobrazení Backstage](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md)  
  
  
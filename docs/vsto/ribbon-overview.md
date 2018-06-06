---
title: Přehled pásu karet
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- customizing the Ribbon, multiple Ribbons
- Ribbon [Office development in Visual Studio], about Ribbon
- toolbars [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], multiple Ribbons
- toolbars [Office development in Visual Studio]
- custom Ribbon, multiple Ribbons
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6f78f55f1f36f23331a9e27228c0afa567429e30
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693017"
---
# <a name="ribbon-overview"></a>Přehled pásu karet
  Na pásu karet je způsob, jak uspořádat související příkazy, aby byly snadněji najít. Příkazy se zobrazí jako ovládacích prvků na pásu karet. Ovládací prvky jsou uspořádány do *skupiny* podél vodorovné pruhu na horním okraji okna aplikace. Související skupiny jsou uspořádány na kartách.  
  
 Většina funkcí, které byly zpřístupněny pomocí nabídek a panelů nástrojů v dřívějších verzích systému Microsoft Office je nyní přístupná pomocí pásu karet. Další informace najdete v tématu technického článku [vývojáře přehled uživatelského rozhraní pro systém Microsoft Office 2007](http://go.microsoft.com/fwlink/?LinkID=70860).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="customize-the-microsoft-office-ribbon"></a>Přizpůsobení pásu karet aplikace Microsoft Office  
 Přizpůsobení pásu karet, přidejte jeden z následujících položek pásu karet do projektu Office:  
  
-   **Pás karet (vizuálního návrháře)**  
  
-   **Pás karet (XML)**  
  
 Přizpůsobení pásu karet aplikace Excel, například přidáte položku pásu karet do projektu doplňku VSTO v Excelu.  
  
### <a name="ribbon-visual-designer-item"></a>Položka pásu karet (vizuálního návrháře)  
 **Pásu karet (vizuálního návrháře)** položky poskytuje pokročilé nástroje, které usnadňují návrh a vývoj vlastní pás karet. Použití **pásu karet (vizuálního návrháře)** položky k přizpůsobení pásu karet následujícími způsoby:  
  
-   Přidáte vlastní nebo předdefinované karty na pásu karet.  
  
-   Přidáte vlastní skupiny do vlastní nebo předdefinované karty.  
  
    > [!NOTE]  
    >  Předdefinované karty nebo skupinu je ten, který již existuje na pásu karet z aplikace Microsoft Office. Například **Data** karta je předdefinované karty v aplikaci Excel. **Připojení** skupiny je předdefinovaná skupina na **Data** kartě.  
  
-   Přidáte vlastní ovládací prvky do vlastní skupiny.  
  
-   Přidáte vlastní ovládací prvky v zobrazení.  
  
 Další informace o přizpůsobení pásu karet pomocí **pásu karet (vizuálního návrháře)** položky najdete v tématu [Návrhář pásu karet](../vsto/ribbon-designer.md).  
  
### <a name="ribbon-xml-item"></a>Položka pásu karet (XML)  
 Použití **pásu karet (XML)** položku, pokud chcete přizpůsobit na pásu karet způsobem, který není podporován **pásu karet (vizuálního návrháře)** položky. Použití **pásu karet (XML)** položky k přizpůsobení pásu karet následujícími způsoby:  
  
-   Přidat *předdefinované* skupin na vlastní kartě nebo předdefinované karty.  
  
-   Přidání ovládacích prvků integrované do vlastní skupiny.  
  
-   Přidáte vlastní kód pro přepsání obslužné rutiny událostí předdefinované ovládacích prvků.  
  
-   Přizpůsobení panelu nástrojů Rychlý přístup.  
  
-   Sdílet přizpůsobení pásu karet mezi doplňku VSTO pomocí kvalifikovaný identifikátor.  
  
 Další informace o přizpůsobení pásu karet pomocí **pásu karet (XML)** položky najdete v tématu [XML karet](../vsto/ribbon-xml.md).  
  
## <a name="export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Export pásu karet z Návrháře pásu karet do kódu XML pásu karet  
 Pokud vytvoříte pásu karet pomocí Návrháře pásu karet a rozhodnout, že chcete přizpůsobit na pásu karet způsoby, **pásu karet (vizuálního návrháře)** položku nepodporuje, můžete exportovat na pásu karet do formátu XML.  
  
 Visual Studio automaticky vytvoří **pásu karet (XML)** položky a naplní souboru XML pásu karet pomocí elementů a atributů pro každý ovládací prvek na pásu karet.  
  
 Ne všechny vlastnosti, které jsou v **vlastnosti** okno návrháře pásu karet se přenesou do souboru XML pásu karet.  Například Visual Studio neexportuje hodnotu **Image** nebo **Text** vlastnost. Je to způsobeno musíte vytvořit metody zpětného volání v souboru kódu pásu karet exportovaný projektu přiřadit bitovou kopii nebo nastavit text ovládacího prvku. Visual Studio automaticky negeneruje metody zpětného volání v rámci procesu exportu.  
  
 Všechny nezměněné výchozí hodnoty vlastností se navíc nezobrazí ve výsledném souboru XML pásu karet.  
  
 Další informace o tom, jak exportovat do kódu XML pásu karet najdete v tématu [postupy: Export pásu karet z Návrháře pásu karet do kódu XML pásu karet](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md).  
  
### <a name="update-the-code"></a>Aktualizujte kód  
 Je do nového souboru kódu pásu karet **Průzkumníku řešení**. Tento soubor obsahuje třídu XML pásu karet. Je nutné vytvořit metody zpětného volání v `Ribbon Callbacks` oblast této třídy pro zpracování akce uživatele, například kliknutí na tlačítko. Přesun kódu z obslužné rutiny událostí do tyto metody zpětného volání a upravte kód pro práci s programovací model rozšiřitelnosti pásu karet (RibbonX). Další informace najdete v tématu [XML karet](../vsto/ribbon-xml.md).  
  
 Musíte taky přidat kód pro `ThisAddIn`, `ThisWorkbook`, nebo `ThisDocument` třídu, která přepisuje `CreateRibbonExtensibilityObject` metodu a vrátí XML karet třídy pro aplikace Office.  
  
 Další informace najdete v tématu [XML karet](../vsto/ribbon-xml.md).  
  
## <a name="add-multiple-ribbon-items-to-a-project"></a>Přidání více položek pásu karet do projektu  
 Můžete přidat více než jedna položka pásu karet k jedinému projektu. To je užitečné, pokud chcete provést některý z následujících akcí:  
  
-   Vytvoření pásů karet pro aplikaci Outlook *inspektoři*. Další informace najdete v tématu [přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md).  
  
    > [!NOTE]  
    >  Kontrolor je okno, které se otevře, když uživatelé provádět určité úlohy, jako je například vytváření e-mailové zprávy.  
  
-   Vyberte, které pásu karet zobrazíte za běhu.  
  
### <a name="select-which-ribbons-to-display-at-runtime"></a>Vyberte které pásů karet zobrazíte za běhu  
 Protože projektu mohou obsahovat více než jeden pásu karet, můžete vybrat které pásu karet zobrazíte za běhu.  
  
 Chcete-li vybrat pásu karet zobrazíte za běhu, přepište `CreateRibbonExtensibilityObject` metoda v `ThisAddin`, `ThisWorkbook`, nebo `ThisDocument` třída projektu a vraťte se na pásu karet, které chcete zobrazit. Následující příklad zkontroluje hodnotu pole s názvem `myCondition` a vrátí odpovídající pásu karet.  
  
> [!NOTE]  
>  Vrátí pásu karet, která byla vytvořena pomocí syntaxe použité v tomto příkladu **pásu karet (vizuálního návrháře)** položky. Syntaxe pro vrácení pásu karet, která je vytvořená pomocí **pásu karet (XML)** položky se mírně liší. Další informace o vrácení **pásu karet (XML)** položky najdete v tématu [XML karet](../vsto/ribbon-xml.md).  
  
 Přidejte následující kód:  
  
 [!code-vb[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/VisualBasic/trin_Ribbon_choose_Ribbon_4/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/CSharp/trin_Ribbon_choose_Ribbon_4/ThisWorkbook.cs#1)]  
  
### <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md)|Ukazuje, jak přizpůsobit na pásu karet z aplikace Microsoft Office, přidejte **pásu karet (vizuálního návrháře)** nebo **pásu karet (XML)** položku do projektu Office.|  
|[Návrhář pásu karet](../vsto/ribbon-designer.md)|Popisuje, jak můžete přidat vlastní karty, skupiny a ovládacích prvků na pásu karet z aplikace Microsoft Office pomocí Návrháře pásu karet.|  
|[Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)|Ukazuje, jak vytvořit vlastní pás karet karty pomocí Návrháře pásu karet. Návrhář pásu karet můžete použít k přidání a umisťování ovládacích prvků na vlastní kartě.|  
|[Přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md)|Obsahuje přehled silného typu objektu modelu, který můžete použít k získání a nastavení vlastností ovládacích prvků pásu karet za běhu.|  
|[Návod: Aktualizace ovládacích prvků na pásu karet za běhu](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)|Ukazuje, jak použít objektový model pásu karet aktualizace ovládacích prvků na pásu karet po načtení pásu karet do aplikací Office.|  
|[Přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md)|Obsahuje pokyny k přizpůsobení pásu karet v aplikaci Microsoft Office Outlook.|  
|[Přizpůsobení pásu karet pro aplikaci InfoPath](../vsto/customizing-a-ribbon-for-infopath.md)|Obsahuje pokyny k přizpůsobení pásu karet v aplikaci Microsoft Office InfoPath.|  
|[Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)|Ukazuje, jak zobrazit, skrýt a upravit na pásu karet a povolit uživatelům spustit kód z ovládacích prvků v vlastního podokna úloh, podokna akce nebo oblasti formuláře aplikace Outlook.|  
|[Postupy: Změna polohy karty na pásu karet](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)|Ukazuje, jak chcete-li změnit pořadí karet na pásu karet.|  
|[Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)|Ukazuje, jak přidat skupiny a ovládacích prvků do předdefinované karty.|  
|[Postupy: Přidání ovládacích prvků do zobrazení Backstage](../vsto/how-to-add-controls-to-the-backstage-view.md)|Ukazuje, jak k přidávání ovládacích prvků do nabídky, které se otevře po kliknutí **soubor**.|  
|[Postupy: Přidání Spouštěče dialogového okna do skupiny pásu karet](../vsto/how-to-add-a-dialog-box-launcher-to-a-ribbon-group.md)|Zobrazuje přidání Spouštěče dialogového okna na žádnou skupinu na pásu karet.|  
|[Postupy: Export pásu karet z Návrháře pásu karet do kódu XML pásu karet](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)|Popisuje přizpůsobení pásu karet pokročilé způsoby exportováním pásu karet z Návrháře pásu karet XML.|  
|[Pás karet – XML](../vsto/ribbon-xml.md)|Vysvětluje, jak můžete přizpůsobit pásu karet pomocí kódu XML pásu karet.|  
|[Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)|Demonstruje postup vytvoření vlastní karty pásu karet pomocí **pásu karet (XML)** položky.|  
  
  
---
title: "Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Word | Microsoft Docs"
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
- Office development in Visual Studio, creating your first project
- Word [Office development in Visual Studio], creating your first project
- document-level customizations [Office development in Visual Studio], creating your first project
ms.assetid: ec9f5173-0923-4aee-985a-e760e80eaae3
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6c7992f36f82d7caf56b09b0f6887eed363b6665
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-your-first-document-level-customization-for-word"></a>Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Word
  Tento úvodní návod ukazuje, jak vytvořit přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Word. Funkce, které vytvoříte v tento druh řešení jsou k dispozici jenom v případě, že je otevřený konkrétní dokument. Nelze použít přizpůsobení na úrovni dokumentu provést změny celou aplikaci, například zobrazení novou kartu pásu karet v otevřeném dokumentu.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření projektu dokumentu aplikace Word.  
  
-   Přidávání textu do dokumentu, který je hostován v návrháři Visual Studio.  
  
-   Psaní kódu, který se používá k přidání textu do přizpůsobené dokumentu, při otevření modelu objektů aplikace Word.  
  
-   Sestavení a spuštění projektu to vyzkoušíte.  
  
-   Čistí projekt k odebrání vývojovém počítači sestavení nepotřebných souborů a nastavení zabezpečení.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
  
#### <a name="to-create-a-new-word-document-project-in-visual-studio"></a>K vytvoření nového projektu dokumentu aplikace Word v sadě Visual Studio  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.  
  
4.  V části sada rozšířeného **Office/SharePoint** uzlu, vyberte **Office Add in** uzlu.  
  
5.  V seznamu šablon projektu vyberte projektu dokumentu aplikace Word VSTO.  
  
6.  V **název** zadejte **FirstDocumentCustomization**.  
  
7.  Click **OK**.  
  
     **Visual Studio Tools for Office – Průvodce projektem** otevře.  
  
8.  Vyberte **vytvoříte nový textový dokument**a klikněte na tlačítko **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]vytvoří **FirstDocumentCustomization** projektu a přidá **FirstDocumentCustomization** ThisDocument souboru kódu na projekt a dokumentů. **FirstDocumentCustomization** dokumentu se automaticky otevře v návrháři.  
  
## <a name="closing-and-reopening-the-document-in-the-designer"></a>Zavřete a znovu otevřete dokument v Návrháři  
 Pokud jste úmyslně nebo neúmyslně zavřete dokument v Návrháři při vývoji projektu, můžete ho znovu otevřít.  
  
#### <a name="to-close-and-reopen-the-document-in-the-designer"></a>Zavřete a otevřete jej v Návrháři  
  
1.  Dokument zavřete kliknutím **Zavřít** tlačítko (X) pro návrháře okno.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **ThisDocument** kód soubor a klikněte na tlačítko **Návrhář zobrazení**.  
  
     \-nebo –  
  
     V **Průzkumníku řešení**, dvakrát klikněte **ThisDocument** souboru kódu.  
  
## <a name="adding-text-to-the-document-in-the-designer"></a>Přidávání textu do dokumentu v Návrháři  
 Uživatelské rozhraní (UI) můžete navrhnout vaše přizpůsobení úpravou dokumentu, který je otevřený v návrháři. Můžete například přidat text, tabulky nebo ovládací prvky aplikace Word. Další informace o tom, jak použít Návrháře dotazů najdete v tématu [projektech pro systém Office v prostředí sady Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
#### <a name="to-add-text-to-your-document-by-using-the-designer"></a>Chcete-li přidat text do dokumentu pomocí návrháře  
  
1.  V dokumentu, který je otevřený v Návrháři zadejte následující text.  
  
     **Tento text byl přidán pomocí návrháře.**  
  
## <a name="adding-text-to-the-document-programmatically"></a>Přidávání textu do dokumentů prostřednictvím kódu programu  
 Dál přidejte kód do souboru kódu ThisDocument. Nový kód používá model objektů aplikace Word přidat druhý odstavec textu do dokumentu. Ve výchozím nastavení soubor ThisDocument kód obsahuje následující generovaný kód:  
  
-   Částečné definice `ThisDocument` třída, která představuje programovací model dokumentu a poskytuje přístup k modelu objektů aplikace Word. Další informace najdete v tématu [hostitelská položka Document](../vsto/document-host-item.md) a [přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md). Zbývající část `ThisDocument` třída definovaná v souboru skrytá kódu, který byste neměli upravovat.  
  
-   `ThisDocument_Startup` a `ThisDocument_Shutdown` obslužné rutiny událostí. Tyto obslužné rutiny událostí jsou volána, když je dokument otevřít a uzavřen. Použití těchto obslužných rutin událostí k chybě při inicializaci vlastní při otevření dokumentu a vyčištění prostředků, které používají vlastní při zavření dokumentu. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
#### <a name="to-add-a-second-paragraph-of-text-to-the-document-by-using-code"></a>Chcete-li přidat druhý odstavec textu do dokumentu pomocí kódu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **ThisDocument**a potom klikněte na **kód zobrazení**.  
  
     Otevření souboru kódu v sadě Visual Studio.  
  
2.  Nahraďte `ThisDocument_Startup` obslužné rutiny události s následujícím kódem. Po otevření dokumentu tento kód přidá druhý odstavec textu do dokumentu.  
  
     [!code-vb[Trin_WordDocumentTutorial#1](../vsto/codesnippet/VisualBasic/FirstDocumentCustomization/ThisDocument.vb#1)]
     [!code-csharp[Trin_WordDocumentTutorial#1](../vsto/codesnippet/CSharp/FirstDocumentCustomization/ThisDocument.cs#1)]  
  
    > [!NOTE]  
    >  Tento kód používá pro přístup k v prvním odstavci index Hodnota 1 <xref:Microsoft.Office.Tools.Word.Document.Paragraphs%2A> vlastnost. Visual Basic a Visual C# použít pole založené na 0, dolní meze pole většina kolekcí ve model objektů aplikace Word je 1. Další informace najdete v tématu [psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md).  
  
## <a name="testing-the-project"></a>Testování projektu  
  
#### <a name="to-test-your-document"></a>K testování dokumentu  
  
1.  Stiskněte klávesu **F5** sestavení a spuštění projektu.  
  
     Při sestavování projektu se zkompilovat kód do sestavení, které je přidružené k dokumentu. Visual Studio převádí kopii dokumentu a sestavení v zadané výstupní složce sestavení projektu a nakonfiguruje nastavení zabezpečení na vývojovém počítači za účelem přizpůsobení ke spuštění. Další informace najdete v tématu [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
2.  V dokumentu ověřte, že vidíte následující text.  
  
     **Tento text byl přidán pomocí návrháře.**  
  
     **Tento text byl přidán pomocí kódu.**  
  
3.  Zavřete dokument.  
  
## <a name="cleaning-up-the-project"></a>Čištění projektu  
 Po dokončení vývoj projektu, byste měli odebrat soubory v zadané výstupní složce sestavení a nastavení zabezpečení vytvořené procesu sestavení.  
  
#### <a name="to-clean-up-the-completed-project-on-your-development-computer"></a>Vyčistěte dokončený projekt na vývojovém počítači  
  
1.  V sadě Visual Studio na **sestavení** nabídky, klikněte na tlačítko **Vyčistit řešení**.  
  
## <a name="next-steps"></a>Další kroky  
 Teď, když jste vytvořili základní přizpůsobení na úrovni dokumentu ve Wordu, další informace o tom, jak vyvíjet přizpůsobení z těchto témat:  
  
-   Obecné programování úlohy, které můžete provádět v přizpůsobeních na úrovni dokumentu: [programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).  
  
-   Úlohy programování, které jsou specifické pro přizpůsobení na úrovni dokumentu ve Wordu: [řešení pro aplikaci Word](../vsto/word-solutions.md).  
  
-   Pomocí modelu objektů aplikace Word: [přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md).  
  
-   Přizpůsobení uživatelského rozhraní aplikace Word, například pomocí vytvoření vlastní karty na pásu karet nebo vytvoření vlastního podokna akce: [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
-   Pomocí rozšířených objektů aplikace Word poskytované řešení pro systém Office v sadě Visual Studio k provádění úloh, které nejsou možné pomocí model objektů aplikace Word (například hostování spravovaných ovládacích prvků v dokumentech a ovládací prvky aplikace Word vazba na data pomocí daty Windows Forms Vazba modelu): [automatizace aplikace Word pomocí rozšířených objekty](../vsto/automating-word-by-using-extended-objects.md).  
  
-   Sestavování a ladění přizpůsobení na úrovni dokumentu ve Wordu: [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
-   Nasazení přizpůsobení na úrovni dokumentu ve Wordu: [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled vývoje řešení pro systém Office &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Řešení aplikace Word](../vsto/word-solutions.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)   
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md)  
  
  
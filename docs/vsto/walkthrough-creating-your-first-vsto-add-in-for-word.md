---
title: 'Návod: Vytvoření vaší první Add-in VSTO pro Word'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- add-ins [Office development in Visual Studio], creating your first project
- Word [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 22e44ace13e0f70bf74b71f17975b3a45cb76471
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845844"
---
# <a name="walkthrough-create-your-first-vsto-add-in-for-word"></a>Návod: Vytvoření vaší první Add-in VSTO pro Word
  Tento úvodní návod ukazuje, jak vytvořit doplňku VSTO pro aplikaci Microsoft Office Word. Funkce, které vytvoříte v tento druh řešení jsou k dispozici pro aplikace, samostatně, bez ohledu na to, které jsou otevřené dokumenty.  
  
 [!INCLUDE[appliesto_wdallapp](../vsto/includes/appliesto-wdallapp-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření projektu doplňku VSTO pro Word.  
  
-   Psaní kódu, který používá model objektů aplikace Word k přidání textu do dokumentu při jeho uložení.  
  
-   Sestavení a spuštění projektu to vyzkoušíte.  
  
-   Čistí dokončený projekt tak, aby doplňku VSTO již nebude automaticky spustí na svém vývojovém počítači.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="create-the-project"></a>Vytvoření projektu  
  
### <a name="to-create-a-new-word-vsto-add-in-project-in-visual-studio"></a>K vytvoření nového projektu doplňku VSTO pro Word v sadě Visual Studio  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.  
  
4.  V části sada rozšířeného **Office/SharePoint** uzlu, vyberte **Office Add in** uzlu.  
  
5.  V seznamu šablon projektu vyberte projektu doplňku VSTO pro Word.  
  
6.  V **název** zadejte **FirstWordAddIn**.  
  
7.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] vytvoří **FirstWordAddIn** projektu a otevře soubor ThisAddIn kódu v editoru.  
  
## <a name="write-code-to-add-text-to-the-saved-document"></a>Psaní kódu přidat text do uložený dokument  
 Dál přidejte kód do souboru kódu ThisAddIn. Nový kód používá k přidání často používaný text do každého dokumentu uloženého v objektovém modelu aplikace Word. Ve výchozím nastavení soubor ThisAddIn kód obsahuje následující generovaný kód:  
  
-   Částečné definice `ThisAddIn` třídy. Tato třída představuje vstupní bod pro kód a poskytuje přístup k modelu objektů aplikace Word. Další informace najdete v tématu [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md). Zbývající část `ThisAddIn` třída definovaná v souboru skrytá kódu, který byste neměli upravovat.  
  
-   `ThisAddIn_Startup` a `ThisAddIn_Shutdown` obslužné rutiny událostí. Tyto obslužné rutiny událostí jsou volány při Word načte a uvolní vaší doplňku VSTO. Pomocí těchto obslužných rutin událostí k chybě při inicializaci doplňku VSTO, když je načten a vyčistit prostředky využívané třídou vaší doplňku VSTO v případě, že je odpojen. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
### <a name="to-add-a-paragraph-of-text-to-the-saved-document"></a>Chcete-li přidat odstavec textu v uloženém dokumentu  
  
1.  V souboru kódu ThisAddIn, přidejte následující kód, který `ThisAddIn` třídy. Nový kód definuje obslužnou rutinu události pro <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> událost, která se vyvolá, když se dokument uloží.  
  
     Pokud uživatel ukládá dokument, obslužné rutiny události přidá nový text na začátku dokumentu.  
  
     [!code-vb[Trin_WordAddInTutorial#1](../vsto/codesnippet/VisualBasic/FirstWordAddIn/ThisAddIn.vb#1)]
     [!code-csharp[Trin_WordAddInTutorial#1](../vsto/codesnippet/CSharp/FirstWordAddIn/ThisAddIn.cs#1)]  
  
    > [!NOTE]  
    >  Tento kód používá pro přístup k v prvním odstavci hodnotou indexu 1 <xref:Microsoft.Office.Interop.Word._Document.Paragraphs%2A> kolekce. Visual Basic a Visual C# použít pole založené na 0, dolní meze pole většina kolekcí ve model objektů aplikace Word je 1. Další informace najdete v tématu [psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md).  
  
2.  Pokud používáte C#, přidat následující požadované kód, který `ThisAddIn_Startup` obslužné rutiny události. Tento kód se používá k připojení `Application_DocumentBeforeSave` obslužné rutiny události s <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> událostí.  
  
     [!code-csharp[Trin_WordAddInTutorial#2](../vsto/codesnippet/CSharp/FirstWordAddIn/ThisAddIn.cs#2)]  
  
 Předchozí příklady kódu k úpravě dokumentu při jeho uložení, použijte následující objekty:  
  
-   `Application` Pole z `ThisAddIn` třídy. `Application` Pole vrátí <xref:Microsoft.Office.Interop.Word.Application> objekt, který představuje aktuální instanci aplikace Word.  
  
-   `Doc` Parametr obslužné rutiny události pro <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> událostí. `Doc` Parametr <xref:Microsoft.Office.Interop.Word.Document> objekt, který reprezentuje uložený dokument. Další informace najdete v tématu [přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md).  
  
## <a name="test-the-project"></a>Testování projektu  
  
### <a name="to-test-the-project"></a>Otestování projektu  
  
1.  Stiskněte klávesu **F5** sestavení a spuštění projektu.  
  
     Při sestavování projektu se zkompilovat kód do sestavení, které je součástí složku výstupu sestavení pro projekt. Visual Studio také vytvoří sadu položky registru, které umožňují Word zjišťovat a načíst doplňku VSTO a nakonfiguruje nastavení zabezpečení na vývojovém počítači povolit doplňku VSTO ke spuštění. Další informace najdete v tématu [řešení pro systém Office sestavení](../vsto/building-office-solutions.md).  
  
2.  V aplikaci Word uloží aktivní dokument.  
  
3.  Ověřte, zda je přidána následující text k dokumentu.  
  
     **Tento text byl přidán pomocí kódu.**  
  
4.  Zavřete aplikace Word.  
  
## <a name="clean-up-the-project"></a>Vyčistěte projekt  
 Po dokončení vývoj projektu, odeberte z vývojovém počítači doplňku VSTO sestavení, položky registru a nastavení zabezpečení. V opačném doplňku VSTO bude nadále spouštět při každém otevření aplikace Word ve svém vývojovém počítači.  
  
### <a name="to-clean-up-the-completed-project-on-your-development-computer"></a>Vyčistěte dokončený projekt na vývojovém počítači  
  
1.  V sadě Visual Studio na **sestavení** nabídky, klikněte na tlačítko **Vyčistit řešení**.  
  
## <a name="next-steps"></a>Další kroky  
 Teď, když jste vytvořili základní Add-in VSTO pro Word, další informace o tom, jak vyvíjet doplňků VSTO z těchto témat:  
  
-   Obecné programování úlohy, které můžete provádět v doplňcích VSTO: [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md).  
  
-   Úlohy programování, které jsou specifické pro doplňků VSTO pro Word: [aplikace Word řešení](../vsto/word-solutions.md).  
  
-   Pomocí modelu objektů aplikace Word: [přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md).  
  
-   Přizpůsobení uživatelského rozhraní aplikace Word, například pomocí vytvoření vlastní karty na pásu karet nebo vytváření vlastních vlastního podokna úloh: [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
-   Sestavování a ladění doplňků VSTO pro Word: [řešení pro systém Office sestavení](../vsto/building-office-solutions.md).  
  
-   Nasazení doplňků VSTO pro Word: [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také:  
 [Přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Řešení aplikace Word](../vsto/word-solutions.md)   
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Sestavení řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md)  
  
  
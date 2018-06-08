---
title: 'Návod: Vytvoření vazby na data ze služby v projektu doplňku VSTO'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d3c7ed095d0efe756e7a23409cd5a54f9e6dcda8
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845870"
---
# <a name="walkthrough-bind-to-data-from-a-service-in-a-vsto-add-in-project"></a>Návod: Vytvoření vazby na data ze služby v projektu doplňku VSTO
  Data můžete vázat na hostitelské ovládací prvky v projekty doplňku VSTO. Tento návod ukazuje, jak přidání ovládacích prvků do dokumentu aplikace Microsoft Office Word, vytvoření vazby ovládacích prvků k datům získaný ze služby MSDN obsahu a reakce na události v době běhu.  
  
 **Platí pro:** informace v tomto tématu se vztahují na projekty na úrovni aplikace pro Word 2010. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Přidání <xref:Microsoft.Office.Tools.Word.RichTextContentControl> ovládacího prvku do dokumentu za běhu.  
  
-   Vytvoření vazby <xref:Microsoft.Office.Tools.Word.RichTextContentControl> řízení k datům z webové služby.  
  
-   Neodpovídá na požadavky <xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering> události <xref:Microsoft.Office.Tools.Word.RichTextContentControl> ovládacího prvku.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] nebo [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="create-a-new-project"></a>Vytvoření nového projektu  
 Prvním krokem je vytvoření projektu doplňku VSTO pro Word.  
  
### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu doplňku VSTO pro Word s názvem **služba obsah MTPS**, pomocí Visual Basic a C#.  
  
     Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Otevře se Visual Studio `ThisAddIn.vb` nebo `ThisAddIn.cs` souboru a přidá projekt **Průzkumníku řešení**.  
  
## <a name="add-a-web-service"></a>Přidat webovou službu  
 V tomto návodu pomocí webové služby, se nazývá MTPS obsahu služba. Tato webová služba vrací informace ze zadaného článku na webu MSDN v podobě řetězce XML nebo prostý text. Později ukazuje, jak zobrazovat vráceném informace v obsahu ovládacího prvku.  
  
### <a name="to-add-the-mtps-content-service-to-the-project"></a>Chcete-li přidat službu MTPS obsah do projektu  
  
1.  Na **Data** nabídky, klikněte na tlačítko **přidat nový zdroj dat**.  
  
2.  V **Průvodce konfigurací zdroje dat**, klikněte na tlačítko **služby**a potom klikněte na **Další**.  
  
3.  V **adresu** pole, zadejte následující adresu URL:  
  
     **http://services.msdn.microsoft.com/ContentServices/ContentService.asmx**  
  
4.  Klikněte na tlačítko **přejděte**.  
  
5.  V **Namespace** zadejte **ContentService**a klikněte na tlačítko **OK**.  
  
6.  V **Průvodce přidáním odkazu** dialogové okno, klikněte na tlačítko **Dokončit**.  
  
## <a name="add-a-content-control-and-bind-to-data-at-runtime"></a>Přidání obsahu ovládacího prvku a vytvoření vazby na data za běhu  
 V doplňku VSTO projekty můžete přidat a vytvoření vazby ovládacích prvků za běhu. Pro účely tohoto postupu nakonfigurujte obsahu ovládacího prvku k načtení dat z webové služby, když uživatel klikne v ovládacím prvku.  
  
### <a name="to-add-a-content-control-and-bind-to-data"></a>Přidání obsahu ovládacího prvku a vytvoření vazby na data  
  
1.  V `ThisAddIn` třídy, přidejte proměnné pro tuto službu obsah MTPS, obsah ovládacího prvku a datové vazby.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#2)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#2)]  
  
2.  Přidejte následující metodu do `ThisAddIn` třídy. Tato metoda vytvoří ovládací prvek obsahu na začátku aktivní dokument.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#4)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#4)]  
  
3.  Přidejte následující metodu do `ThisAddIn` třídy. Tato metoda inicializuje objekty potřebné pro vytvoření a odeslání požadavku na webovou službu.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#6)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#6)]  
  
4.  Vytvoření obslužné rutiny události pro načtení dokumentu knihovny MSDN o obsahu ovládacích prvků, když uživatel klikne v rámci obsah řízení a vytvoření vazby dat k ovládacímu prvku obsahu.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#5)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#5)]  
  
5.  Volání `AddRichTextControlAtRange` a `InitializeServiceObjects` metody z `ThisAddIn_Startup` metoda. Pro programátory v C# jazyce přidejte obslužnou rutinu události.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#3)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#3)]  
  
## <a name="test-the-add-in"></a>Testování v aplikaci  
 Při otevření aplikace Word, <xref:Microsoft.Office.Tools.Word.RichTextContentControl> ovládací prvek se zobrazí. Text v řízení změny, po kliknutí na tlačítko uvnitř ho.  
  
### <a name="to-test-the-vsto-add-in"></a>K testování doplňku VSTO  
  
1.  Stiskněte klávesu **F5**.  
  
2.  Klikněte na uvnitř obsahu ovládacího prvku.  
  
     Informace o stáhli ze služby MTPS obsah a zobrazit uvnitř obsahu ovládacího prvku.  
  
## <a name="see-also"></a>Viz také:  
 [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  
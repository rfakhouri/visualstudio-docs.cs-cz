---
title: "Návod: Zobrazení textu v textovém poli v dokumentu s použitím tlačítka | Microsoft Docs"
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
helpviewer_keywords: text boxes, displaying text in documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 803dcbe27eedc4b93443a6389b4acf7ee2dc08cf
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button"></a>Návod: Zobrazení textu v textovém poli v dokumentu s použitím tlačítka
  Tento návod ukazuje, jak používat tlačítka a textová pole v přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Přidání ovládacích prvků do dokumentů aplikace Word v projektech na úrovni dokumentu v době návrhu.  
  
-   Při kliknutí na tlačítko, vyplní textové pole.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
 Prvním krokem je vytvoření projektu dokument aplikace Word.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu dokument aplikace Word s názvem **Moje tlačítko slovo**. V průvodci vyberte **vytvoříte nový textový dokument**.  
  
     Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nový dokument aplikace Word v návrháři a přidá **Moje tlačítko slovo** projektu do **Průzkumníku řešení**.  
  
## <a name="adding-controls-to-the-word-document"></a>Přidání ovládacích prvků do dokumentů aplikace Word  
 Ovládacích prvků uživatelského rozhraní se skládá z tlačítka a do textového pole na dokument aplikace Word.  
  
#### <a name="to-add-a-button-and-a-text-box"></a>Přidání tlačítka a textové pole  
  
1.  Ověřte, že dokument otevřít v návrháři Visual Studio.  
  
2.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte ji <xref:Microsoft.Office.Tools.Word.Controls.TextBox> ovládací prvek v dokumentu.  
  
    > [!NOTE]  
    >  V aplikaci Word, ovládací prvky zahozených v řádku s textem ve výchozím nastavení. Můžete upravit způsob ovládací prvky a tvar objekty jsou vloženy změnou výchozího na **upravit** kartě **možnosti** dialogové okno v aplikaci Word.  
  
3.  Na **zobrazení** nabídky, klikněte na tlačítko **vlastnosti – okno**.  
  
4.  Najít **TextBox1** v **vlastnosti** okno rozevíracího seznamu a změňte **název** vlastnosti textového pole na **ZobrazenýText**.  
  
5.  Přetáhněte **tlačítko** řízení k dokumentu a změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**insertText**|  
    |**Text**|**Zadejte Text**|  
  
 Teď můžete napsat kód, který se spustí při kliknutí na tlačítko.  
  
## <a name="populating-the-text-box-when-the-button-is-clicked"></a>Při kliknutí na tlačítko naplnění textového pole  
 Pokaždé, když uživatel klikne na tlačítko **Hello, World!** je přidán do textového pole.  
  
#### <a name="to-write-to-the-text-box-when-the-button-is-clicked"></a>Při kliknutí na tlačítko zapsat do textového pole  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **ThisDocument**a potom klikněte na **kód zobrazení** v místní nabídce.  
  
2.  Přidejte následující kód, který <xref:System.Windows.Forms.Control.Click> obslužné rutiny události tlačítka.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#7](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#7)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#7](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#7)]  
  
3.  V jazyce C#, je nutné přidat obslužné rutiny události pro tlačítka <xref:Microsoft.Office.Tools.Word.Document.Startup> událostí. Informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#8](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#8)]  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Nyní můžete otestovat, ujistěte se, že váš dokument zprávu **Hello, World!** v textovém poli se zobrazí, když kliknete na tlačítko.  
  
#### <a name="to-test-your-document"></a>K testování dokumentu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Klikněte na tlačítko.  
  
3.  Potvrďte, že **Hello World!** Zobrazí se v textovém poli.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základy používání tlačítka a textová pole na dokumenty aplikace Word. Zde jsou některé úlohy, které by mohl pocházet Další:  
  
-   Chcete-li změnit formátování pomocí pole se seznamem. Další informace najdete v tématu [návod: Změna dokumentu formátování pomocí ovládacích prvků CheckBox](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md).  
  
-   Pomocí přepínačů vyberte styly grafu. Další informace najdete v tématu [návod: aktualizace grafu v dokumentu pomocí tlačítka přepínač](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md).  
  
## <a name="see-also"></a>Viz také  
 [Windows Forms – ovládací prvky na přehled dokumenty sady Office](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Návody pro práci s aplikací Word](../vsto/walkthroughs-using-word.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Postupy: Přidání ovládacích prvků do dokumentů Office Windows Forms](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)  
  
  
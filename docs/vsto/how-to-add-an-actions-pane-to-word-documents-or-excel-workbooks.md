---
title: "Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel | Microsoft Docs"
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
- smart documents [Office development in Visual Studio], creating in Word
- smart documents [Office development in Visual Studio], adding controls
- actions panes [Office development in Visual Studio], creating in Word
- actions panes [Office development in Visual Studio], adding controls
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d259442104cfbd6b072d0068ab5f2b4f182f027f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks"></a>Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel
  Chcete-li přidat podokna akcí do dokumentu aplikace Microsoft Office Word nebo sešitu aplikace Microsoft Excel, nejdřív vytvořte uživatelského ovládacího prvku Windows Forms. Pak přidat uživatelský ovládací prvek na <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> vlastnost `ThisDocument.ActionsPane` pole (Word) nebo `ThisWorkbook.ActionsPane` pole (aplikace Excel) ve vašem projektu.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="creating-the-user-control"></a>Vytvoření uživatelského ovládacího prvku  
 Následující postup ukazuje postup vytvoření uživatelského ovládacího prvku v textovém nebo projektu aplikace Excel. Také přidá tlačítko do uživatelského ovládacího prvku, který zapíše text do dokumentu nebo sešitu po klepnutí.  
  
#### <a name="to-create-the-user-control"></a>Vytvoření uživatelského ovládacího prvku  
  
1.  Otevřete projekt úrovni dokumentu Word či Excel v sadě Visual Studio.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogové okno, vyberte **ovládací prvek podokna akce**, pojmenujte ji **HelloControl**a klikněte na tlačítko **přidat**.  
  
    > [!NOTE]  
    >  Případně můžete přidat **uživatelský ovládací prvek** položku do projektu. Třídy generované **ovládací prvek podokna akce** a **uživatelský ovládací prvek** položky jsou funkčně rovnocenné.  
  
4.  Z **Windows Forms** kartě **sada nástrojů,** přetáhněte **tlačítko** ovládacího prvku do ovládacího prvku.  
  
    > [!NOTE]  
    >  Pokud ovládací prvek není viditelná v návrháři, dvakrát klikněte na tlačítko **HelloControl** v **Průzkumníku řešení**.  
  
5.  Přidejte kód, který <xref:System.Windows.Forms.Control.Click> obslužné rutiny události tlačítka. Následující příklad ukazuje kód pro dokument aplikace Microsoft Office Word.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#12](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/HelloControl.cs#12)]
     [!code-vb[Trin_VstcoreActionsPaneWord#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/HelloControl.vb#12)]  
  
6.  V jazyce C# je nutné přidat obslužné rutiny události pro klikněte na tlačítko. Tento kód můžete umístit `HelloControl` konstruktor po volání `IntializeComponent`.  
  
     Informace o tom, jak vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#13](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/HelloControl.cs#13)]  
  
## <a name="adding-the-user-control-to-the-actions-pane"></a>Přidání uživatelského ovládacího prvku do podokna akce  
 Pokud chcete zobrazit v podokně Akce, přidat uživatelský ovládací prvek na <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> vlastnost `ThisDocument.ActionsPane` pole (Word) nebo `ThisWorkbook.ActionsPane` pole (aplikace Excel).  
  
#### <a name="to-add-the-user-control-to-the-actions-pane"></a>Chcete-li přidat uživatelský ovládací prvek do podokna akce  
  
1.  Přidejte následující kód, který `ThisDocument` nebo `ThisWorkbook` třída jako deklaraci úrovni třídy (nepřidávejte tento kód do metody).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#14](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#14)]
     [!code-vb[Trin_VstcoreActionsPaneWord#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#14)]  
  
2.  Přidejte následující kód, který `ThisDocument_Startup` obslužnou rutinu události `ThisDocument` – třída nebo `ThisWorkbook_Startup` obslužnou rutinu události `ThisWorkbook` – třída.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#15](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#15)]
     [!code-vb[Trin_VstcoreActionsPaneWord#15](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#15)]  
  
## <a name="see-also"></a>Viz také  
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)   
 [Návod: Vložení textu do dokumentu z podokna akcí](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [Postupy: Správa rozložení ovládacích prvků v podoknech akcí](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [Návod: Vložení textu do dokumentu z podokna akcí](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
  
  
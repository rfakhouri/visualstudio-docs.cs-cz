---
title: 'Postupy: Správa rozložení ovládacích prvků v podoknech akcí'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- actions panes [Office development in Visual Studio], control layout
- controls [Office development in Visual Studio], layout on actions panes
- smart documents [Office development in Visual Studio], control layout
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: ee790707a5c1c74f3227f74874c66bb4438e7ab0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53991172"
---
# <a name="how-to-manage-control-layout-on-actions-panes"></a>Postupy: Správa rozložení ovládacích prvků v podoknech akcí
  Podokna akcí je ukotven na pravém rohu dokumentu nebo sešitu ve výchozím nastavení; ale ho lze ukotvit vlevo, horní nebo dolní. Pokud používáte více uživatelských ovládacích prvků, můžete napsat kód správně zásobníku uživatelské ovládací prvky v podokně Akce. Další informace najdete v tématu [přehled podokna akcí](../vsto/actions-pane-overview.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Zásobník pořadí ovládacích prvků závisí na, jestli je ukotven v podokně Akce vodorovně nebo svisle.  
  
> [!NOTE]  
>  Pokud uživatel změní velikost podokna akcí za běhu, můžete nastavit ovládací prvky pro změnu velikosti s podoknem akcí. Můžete použít <xref:System.Windows.Forms.Control.Anchor%2A> vlastnost ovládacího prvku Windows Forms do ovládacích prvků ukotvení pro podokna akcí. Další informace najdete v tématu [jak: Ukotvení ovládacích prvků ve Windows Forms](/dotnet/framework/winforms/controls/how-to-anchor-controls-on-windows-forms).  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="to-set-the-stack-order-of-the-actions-pane-controls"></a>K nastavení pořadí zásobníku ovládacích prvků podokna akce  
  
1.  Otevřete projekt úrovni dokumentu pro aplikaci Microsoft Office Word, který zahrnuje podokna akcí s více uživatelských ovládacích prvků nebo vnořené akce podokna ovládacích prvků. Další informace najdete v tématu [jak: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md).  
  
2.  Klikněte pravým tlačítkem na **ThisDocument.cs** nebo **ThisDocument.vb** v **Průzkumníka řešení** a potom klikněte na tlačítko **zobrazit kód**.  
  
3.  V <xref:Microsoft.Office.Tools.ActionsPane.OrientationChanged> obslužná rutina události z podokna akcí, zkontrolujte, jestli je vodorovné orientaci ovládacího prvku podokna akcí.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#30](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#30)]
     [!code-vb[Trin_VstcoreActionsPaneWord#30](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#30)]  
  
4.  Při vodorovné orientace zásobníku v podokně Akce řídí z levé strany; v opačném případě z horní části zásobníku je.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#31](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#31)]
     [!code-vb[Trin_VstcoreActionsPaneWord#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#31)]  
  
5.  V C#, je nutné přidat obslužnou rutinu události pro `ActionsPane` k <xref:Microsoft.Office.Tools.Word.Document.Startup> obslužné rutiny události. Informace o vytváření obslužných rutin událostí, naleznete v tématu [jak: Vytváření obslužných rutin událostí v projektech pro systém Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#32](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#32)]  
  
6.  Spusťte projekt a ověřte, že jsou ovládací prvky podokna akce při podokna akcí je ukotven v horní části dokumentu a ovládací prvky jsou skládané shora dolů, když v podokně Akce je ukotven na pravé straně dokumentu skládaný zleva doprava.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_VstcoreActionsPaneWord#29](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#29)]
 [!code-vb[Trin_VstcoreActionsPaneWord#29](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#29)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Určuje projekt úrovni dokumentu aplikace Word se podokna akcí, která obsahuje více uživatelských ovládacích prvků nebo podokně vnořená akce.  
  
## <a name="see-also"></a>Viz také:  
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)   
 [Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo Excelové sešity](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Návod: Vkládání textu do dokumentu z podokna akcí](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [Návod: Vkládání textu do dokumentu z podokna akcí](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  

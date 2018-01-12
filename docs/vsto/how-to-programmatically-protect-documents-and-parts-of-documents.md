---
title: "Postupy: zamykání dokumentů a částí dokumentů | Microsoft Docs"
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
- document protection
- documents [Office development in Visual Studio], document protection
- Word documents, protection
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8655a03659bd3b69e23fd155620d42df6d52386c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-protect-documents-and-parts-of-documents"></a>Postupy: Zamykání dokumentů a částí dokumentů prostřednictvím kódu programu
  Ochranu můžete přidat do dokumentů aplikace Microsoft Office Word uživatelům zabránit v provádět veškeré úpravy dokumentu.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Některé oblasti dokumentu lze také označit jako výjimky tak, aby zadaný uživatelé mohou upravovat pouze ty oblasti dokumentu. Například můžete chtít chránit celý dokument s výjimkou konkrétní záložku. Volitelně můžete přidat heslo, aby uživatelé nelze odebrat ochranu dokumentů, pokud neznají heslo.  
  
> [!NOTE]  
>  Následující příklad nepoužívá ochrana heslem; Můžete ale chtít zvažte použití hesla při přidávání ochrana dokumentu. Další informace najdete v tématu dokument ochranu ukázku najdete na adrese [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
 Ovládací prvky obsahu můžete použít také k ochraně částí dokumentů. Další informace najdete v tématu [postupy: ochrana částí z dokumentů pomocí ovládacích prvků obsahu](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md).  
  
## <a name="protecting-a-document-that-is-part-of-a-document-level-customization"></a>Ochrana dokumentu, který je součástí přizpůsobení na úrovni dokumentu  
  
#### <a name="to-protect-a-document-that-is-part-of-a-document-level-customization"></a>Ochrana dokumentu, který je součástí přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.Protect%2A> metodu `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#111](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#111)]
     [!code-csharp[Trin_VstcoreWordAutomation#111](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#111)]  
  
#### <a name="to-exclude-a-bookmark-control-from-document-protection"></a>Vyloučit z ochrany dokumentu ovládacího prvku záložek  
  
1.  Chránit pomocí celý dokument <xref:Microsoft.Office.Tools.Word.Document.Protect%2A> metoda.  
  
     [!code-vb[Trin_VstcoreWordAutomation#111](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#111)]
     [!code-csharp[Trin_VstcoreWordAutomation#111](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#111)]  
  
2.  Vyloučit `Bookmark1` z ochrany dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#112](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#112)]
     [!code-csharp[Trin_VstcoreWordAutomation#112](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#112)]  
  
### <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Pokud chcete použít tyto příklady kódu, spusťte z `ThisDocument` třídy ve vašem projektu. Tyto příklady kódu předpokládá, že už máte existující <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek s názvem `Bookmark1` v dokumentu, ve kterém se zobrazí tento kód.  
  
## <a name="protecting-a-document-by-using-an-vsto-add-in"></a>Ochrana dokumentu pomocí doplňku VSTO  
  
#### <a name="to-protect-a-document-by-using-an-application-level-vsto-add-in"></a>Ochrana dokumentu pomocí doplňku VSTO úrovni aplikace  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.Protect%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> , které chcete chránit.  
  
     Následující příklad kódu chrání aktivní dokument. Chcete-li použít tento příklad kódu, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#111](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#111)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#111](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#111)]  
  
## <a name="see-also"></a>Viz také  
 [Ochrana dokumentů v řešeních na úrovni dokumentu](../vsto/document-protection-in-document-level-solutions.md)   
 [Ochrana heslem v dokumentech Office](../vsto/password-protection-on-office-documents.md)   
 [Postupy: povolení kódu spuštění na pozadí dokumentů s omezenými oprávněními](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Navrhování a tvorba řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)  
  
  
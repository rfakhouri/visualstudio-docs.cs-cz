---
title: "Řešení aplikace Word | Microsoft Docs"
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
- solutions [Office development in Visual Studio], Word
- Office projects [Office development in Visual Studio], Word
- application-level add-ins [Office development in Visual Studio], Word
- Word [Office development in Visual Studio]
- projects [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], about Word solutions
- Office solutions [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], application-level add-ins
- documents [Office development in Visual Studio], Word
- Office development in Visual Studio, Word solutions
- add-ins [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], document-level customizations
- user interfaces [Office development in Visual Studio], Word
- Office documents [Office development in Visual Studio, Word
- document-level customizations [Office development in Visual Studio], Word
ms.assetid: ef339ad8-1897-4a44-b588-e6004d0b6d8b
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 738c7988dbd5ee4757b231904be08dcf295ba5b7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="word-solutions"></a>Řešení pro Word
  Visual Studio poskytuje šablony projektů, které můžete použít k vytvoření přizpůsobení na úrovni dokumentu a doplňků VSTO pro aplikaci Microsoft Office Word. Tato řešení můžete použít k automatizaci aplikace Word, rozšířit funkce aplikace Word a přizpůsobení uživatelského rozhraní (UI) aplikace Word. Další informace o rozdílech mezi úpravy na úrovni dokumentu a doplňků VSTO najdete v tématu [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
 Toto téma poskytuje následující informace:  
  
-   [Automatizace v aplikaci Word](#automating).  
  
-   [Vývoj přizpůsobení na úrovni dokumentu ve Wordu](#doclevel).  
  
-   [Vývoj doplňků VSTO pro Word](#applevel).  
  
-   [Přizpůsobení uživatelského rozhraní aplikace Word](#UI).  
  
##  <a name="automating"></a>Automatizace aplikace Word  
 Model objektů aplikace Word zpřístupní mnoho typů, které můžete použít k automatizaci aplikace Word. Například můžete prostřednictvím kódu programu vytvářet tabulky, formátování dokumentů a nastavit text v rozsahy a odstavce. Další informace najdete v tématu [přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md).  
  
 Při vývoji řešení aplikace Word v sadě Visual Studio, můžete také použít *hostitele položky* a *hostování ovládacích prvků* v řešení. Jedná se o objekty, které rozšiřují určité běžně používané objekty ve model objektů aplikace Word, jako <xref:Microsoft.Office.Interop.Word.Document> a <xref:Microsoft.Office.Interop.Word.ContentControl> objekty. Rozšířené objekty chovají jako Word objekty, které jsou založené na, ale přidat další události a možnosti pro datové vazby k objektům. Další informace najdete v tématu [automatizace aplikace Word pomocí rozšířených objekty](../vsto/automating-word-by-using-extended-objects.md).  
  
##  <a name="doclevel"></a>Vývoj přizpůsobení na úrovni dokumentu pro Word  
 Přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Word se skládá ze sestavení, které souvisí s konkrétním dokumentu. Sestavení obvykle rozšiřuje dokumentu přizpůsobení uživatelského rozhraní a automatizace aplikace Word. Na rozdíl od Add-in VSTO, který je spojen s aplikací Word, samotné, funkce, které můžete implementovat přizpůsobení je k dispozici jenom v případě, že je otevřený v aplikaci Word přidružené dokument.  
  
 K vytvoření projektu přizpůsobení na úrovni dokumentu ve Wordu, pomocí šablony projektu dokument aplikace Word nebo šablony aplikace Word v **nový projekt** dialogové okno sady Visual Studio. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Další informace o přizpůsobení pracovní jak úrovni dokumentu [architektura z úpravy na úrovni dokumentů](../vsto/architecture-of-document-level-customizations.md).  
  
### <a name="word-customization-programming-model"></a>Model programování přizpůsobení aplikace Word  
 Když vytvoříte projekt na úrovni dokumentu ve Wordu, Visual Studio vygeneruje třídu s názvem `ThisDocument`, což je základ pro vaše řešení. Tato třída reprezentuje dokument, který je spojen s vaším řešením, a poskytuje výchozí bod pro psaní kódu.  
  
 Další informace o `ThisDocument` třídy a další funkce, které můžete použít v projektech na úrovni dokumentu, najdete v části [programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).  
  
##  <a name="applevel"></a>Vývoj doplňků VSTO pro Word  
 VSTO Add-in pro aplikaci Microsoft Office Word se skládá z sestavení zavedená aplikace Word. Sestavení obvykle rozšíří slovo přizpůsobení uživatelského rozhraní a automatizace aplikace Word. Na rozdíl od přizpůsobení na úrovni dokumentu, který je přidružen ke konkrétní dokumentu, není omezen na jednom dokumentu funkce, které můžete implementovat v doplňku VSTO.  
  
 K vytvoření projektu doplňku VSTO pro Word, použití šablon projektu doplňku pro aplikaci Word v **nový projekt** dialogové okno sady Visual Studio. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Obecné informace o fungování doplňků VSTO najdete v tématu [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
### <a name="word-add-in-programming-model"></a>Model programování doplňku aplikace Word  
 Při vytváření projektu doplňku VSTO pro Word, Visual Studio vygeneruje třídu s názvem `ThisAddIn`, což je základ pro vaše řešení. Tato třída poskytuje výchozí bod pro zápis kódu a taky zpřístupňuje objektový model slova pro vaše doplňku VSTO.  
  
 Další informace o `ThisAddIn` třídy a další funkce, které můžete použít VSTO Add-in, najdete v části [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
##  <a name="UI"></a>Přizpůsobení uživatelského rozhraní aplikace Word  
 Přizpůsobení uživatelského rozhraní aplikace Word několika různými způsoby. Některé možnosti jsou k dispozici pro všechny typy projektů a další možnosti jsou k dispozici jenom doplňků VSTO nebo úpravy na úrovni dokumentů.  
  
### <a name="options-for-all-project-types"></a>Možnosti pro všechny typy projektů  
 Následující tabulka uvádí možnosti přizpůsobení, které jsou k dispozici pro úpravy na úrovni dokumentu a doplňků VSTO.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Přizpůsobení pásu karet.|[Přehled pásu karet](../vsto/ribbon-overview.md)|  
|Přidání ovládacích prvků Windows Forms nebo rozšířené ovládací prvky aplikace Word na vlastní dokument (pro přizpůsobení na úrovni dokumentu) nebo otevřete dokumentu (pro modul Add-in VSTO).|[Postupy: Přidání ovládacích prvků Windows Forms do dokumentů Office](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)<br /><br /> [Postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md)<br /><br /> [Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)|  
  
### <a name="options-for-document-level-customizations"></a>Možnosti pro úpravy na úrovni dokumentů  
 Následující tabulka uvádí možnosti přizpůsobení, které jsou k dispozici pouze pro úpravy na úrovni dokumentů.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Přidání podokna akcí v dokumentu.|[Přehled podokna akcí](../vsto/actions-pane-overview.md)<br /><br /> [Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)|  
|Přidáte rozšířené XMLNode a XmlNodes – ovládací prvky na povrch dokument.|[Postupy: Přidání ovládacích prvků XMLNode do dokumentů aplikace Word](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)<br /><br /> [Postupy: Přidání ovládacích prvků XMLNodes do dokumentů aplikace Word](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)|  
  
### <a name="options-for-vsto-add-ins"></a>Možnosti pro doplňky VSTO  
 Následující tabulka uvádí možnosti přizpůsobení, které jsou k dispozici pouze pro doplňky VSTO.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Vytvoření vlastního podokna úloh.|[Vlastní podokona úloh](../vsto/custom-task-panes.md)|  
  
### <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)|Poskytuje přehled hlavních typů poskytované model objektů aplikace Word.|  
|[Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)|Poskytuje informace o rozšířených objektů (poskytované [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]), můžete použít v řešeních pro aplikaci Word.|  
|[Přehled ovládacích prvků modelu Windows Forms v dokumentech Office](../vsto/windows-forms-controls-on-office-documents-overview.md)|Popisuje, jak můžete přidat ovládací prvky Windows Forms do dokumentů aplikace Word.|  
|[Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)|Ukazuje, jak vytvořit základní přizpůsobení na úrovni dokumentu ve Wordu.|  
|[Návody: Vytvoření prvního doplňku VSTO pro Word](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)|Ukazuje, jak vytvořit základní Add-in VSTO ve Wordu.|  
|[Návod: Přidání ovládacích prvků do dokumentu za běhu v doplňku VSTO](../vsto/walkthrough-adding-controls-to-a-document-at-run-time-in-a-vsto-add-in.md)|Ukazuje, jak přidat Windows Forms tlačítko a <xref:Microsoft.Office.Tools.Word.RichTextContentControl> do dokumentu za běhu pomocí doplňku VSTO.|  
|[Wordu 2010 v vývoj pro Office](http://go.microsoft.com/fwlink/?LinkId=199020)|Obsahuje odkazy na články a referenční dokumentaci o vývoj řešení pro aplikaci Word (nejsou specifické pro vývoj pro Office pomocí sady Visual Studio).|  
  
  
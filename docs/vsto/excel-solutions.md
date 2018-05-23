---
title: řešení pro aplikaci Excel
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], application-level add-ins
- Office solutions [Office development in Visual Studio], Excel
- solutions [Office development in Visual Studio], Excel
- add-ins [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], about Excel solutions
- Excel [Office development in Visual Studio]
- documents [Office development in Visual Studio], Excel
- Office documents [Office development in Visual Studio, Excel
- projects [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], document-level customizations
- user interfaces [Office development in Visual Studio], Excel
- Office development in Visual Studio, Excel solutions
- document-level customizations [Office development in Visual Studio], Excel
- Office projects [Office development in Visual Studio], Excel
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8e2c6e25c3acdfb4c90eb0ba74d66670be339588
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="excel-solutions"></a>řešení pro aplikaci Excel
  Visual Studio poskytuje šablony projektů, které můžete použít k vytvoření přizpůsobení na úrovni dokumentu a doplňků VSTO pro aplikaci Microsoft Office Excel. Tato řešení můžete použít k automatizaci aplikace Excel, rozšířit funkce aplikace Excel a přizpůsobení uživatelského rozhraní (UI) aplikace Excel. Další informace o rozdílech mezi úpravy na úrovni dokumentu a doplňků VSTO najdete v tématu [přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
 Toto téma poskytuje následující informace:  
  
-   [Automatizace aplikace Excel](#automating).  
  
-   [Vývoj přizpůsobení na úrovni dokumentu pro Excel](#doclevel).  
  
-   [Vývoj doplňků VSTO pro Excel](#applevel).  
  
-   [Přizpůsobení uživatelského rozhraní aplikace Excel](#UI).  
  
##  <a name="automating"></a> Automatizace aplikace Excel  
 Model objektů aplikace Excel zpřístupní mnoho typů, které můžete použít k automatizaci aplikace Excel. Například můžete prostřednictvím kódu programu vytvářet grafy, formátování listů a nastavte hodnoty rozsahy a buněk. Další informace najdete v tématu [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).  
  
 Při vývoji řešení pro aplikaci Excel v sadě Visual Studio, můžete také použít *hostitele položky* a *hostování ovládacích prvků* v řešení. Jedná se o objekty, které rozšiřují určité běžně používané objekty ve model objektů aplikace Excel, jako <xref:Microsoft.Office.Interop.Excel.Worksheet> a <xref:Microsoft.Office.Interop.Excel.Range> objekty. Rozšířené objekty chovají jako objekty aplikace Excel, které jsou založené na, ale přidat další události a možnosti pro datové vazby k objektům. Další informace najdete v tématu [automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md).  
  
##  <a name="doclevel"></a> Vývoj přizpůsobení na úrovni dokumentu pro Excel  
 Přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Excel se skládá ze sestavení, které souvisí s konkrétním sešitu. Sestavení obvykle rozšiřuje sešit přizpůsobení uživatelského rozhraní a automatizace aplikace Excel. Na rozdíl od Add-in VSTO, která je přidružená aplikace Excel, samotné, funkce, které můžete implementovat přizpůsobení je k dispozici jenom v případě, že je přidružený sešit otevřít v aplikaci Excel.  
  
 K vytvoření projektu přizpůsobení na úrovni dokumentu pro Excel, použijte sešit aplikace Excel nebo Excel šablona projektu šablony v **nový projekt** dialogové okno sady Visual Studio. Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Další informace o přizpůsobení pracovní jak úrovni dokumentu najdete v tématu [architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md).  
  
### <a name="excel-customization-programming-model"></a>Programovací model přizpůsobení aplikace Excel  
 Když vytvoříte projekt na úrovni dokumentu pro Excel, Visual Studio vytvoří několik tříd, které jsou základem řešení: `ThisWorkbook`, `Sheet1`, `Sheet2`, a `Sheet3`. Tyto třídy představují sešit a listy, které jsou spojeny s vaším řešením, a poskytují výchozí bod pro psaní kódu.  
  
 Další informace o těchto generované třídy a další funkce, které můžete použít v projektech na úrovni dokumentu, najdete v části [programu úpravy na úrovni dokumentů](../vsto/programming-document-level-customizations.md).  
  
##  <a name="applevel"></a> Vývoj doplňků VSTO pro Excel  
 VSTO Add-in pro aplikaci Microsoft Office Excel se skládá z sestavení zavedená aplikace Excel. Sestavení obvykle rozšiřuje aplikace Excel, přizpůsobením uživatelského rozhraní a to pomocí automatizace aplikace Excel. Na rozdíl od přizpůsobení na úrovni dokumentu, který je přidružen ke konkrétní sešitu, není omezen na všechny jeden sešit funkce, které můžete implementovat v doplňku VSTO.  
  
 K vytvoření projektu doplňku VSTO pro Excel, použijte sešit aplikace Excel nebo Excel šablona projektu šablony v **nový projekt** dialogové okno sady Visual Studio. Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Obecné informace o fungování doplňků VSTO najdete v tématu [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak automatizovat PowerPoint I: z doplněk aplikace Excel?](http://go.microsoft.com/fwlink/?LinkID=130300).  
  
### <a name="excel-add-in-programming-model"></a>Add-in programovací model v aplikaci Excel  
 Při vytvoření projektu doplňku VSTO v Excelu, Visual Studio vytvoří třídu s názvem `ThisAddIn`, což je základ pro vaše řešení. Tato třída poskytuje výchozí bod pro zápis kódu a taky zpřístupňuje objektový model aplikace Excel k vaší doplňku VSTO.  
  
 Další informace o `ThisAddIn` třídy a další funkce sady Visual Studio můžete použít VSTO Add-in, najdete v části [Program VSTO doplňků](../vsto/programming-vsto-add-ins.md).  
  
##  <a name="UI"></a> Přizpůsobení uživatelského rozhraní aplikace Excel  
 Přizpůsobení uživatelského rozhraní aplikace Excel několika různými způsoby. Některé možnosti jsou k dispozici pro všechny typy projektů a další možnosti jsou k dispozici jenom doplňků VSTO nebo úpravy na úrovni dokumentů.  
  
### <a name="options-for-all-project-types"></a>Možnosti pro všechny typy projektů  
 Následující tabulka uvádí možnosti přizpůsobení, které jsou k dispozici pro úpravy na úrovni dokumentu a doplňků VSTO.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Přizpůsobení pásu karet.|[Přehled pásu karet](../vsto/ribbon-overview.md)|  
|Přidání ovládacích prvků Windows Forms nebo rozšířené ovládací prvky aplikace Excel na list v vlastní sešit pro přizpůsobení na úrovni dokumentu nebo v jakékoli otevřeného sešitu pro doplňku VSTO.|[Postupy: Přidání ovládacích prvků Windows forms do dokumentů Office](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)<br /><br /> [Postupy: Přidání ovládacích prvků graf do listů](../vsto/how-to-add-chart-controls-to-worksheets.md)<br /><br /> [Postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md)<br /><br /> [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)|  
  
### <a name="options-for-document-level-customizations"></a>Možnosti pro úpravy na úrovni dokumentů  
 Následující tabulka uvádí možnosti přizpůsobení, které jsou k dispozici pouze pro úpravy na úrovni dokumentů.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Přidání podokna akcí v sešitu.|[Přehled podokna akcí](../vsto/actions-pane-overview.md)<br /><br /> [Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)|  
|Přidání ovládacích prvků rozšířené rozsahu, které jsou mapované na uzly XML do listu.|[Postupy: Přidání ovládacích prvků XMLMappedRange do listů](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)|  
  
### <a name="options-for-vsto-add-ins"></a>Možnosti pro doplňky VSTO  
 Následující tabulka uvádí možnosti přizpůsobení, které jsou k dispozici pouze pro doplňky VSTO.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Vytvoření vlastního podokna úloh.|[Vlastní podokna úloh](../vsto/custom-task-panes.md)|  
  
### <a name="related-topics"></a>Související témata  
|Název|Popis|  
|-----------|-----------------|  
|[Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)|Poskytuje přehled hlavních typů poskytované model objektů aplikace Excel.|  
|[Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)|Poskytuje informace o rozšířených objektů (poskytované [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]), můžete použít v řešení pro aplikaci Excel.|  
|[Globalizace a lokalizace řešení pro aplikaci Excel](../vsto/globalization-and-localization-of-excel-solutions.md)|Obsahuje informace o zvláštní upozornění pro řešení pro aplikaci Excel, které se budou spouštět v počítačích s jinou než anglickou nastavení pro Windows.|  
|[Ovládací prvky Windows Forms na přehled dokumenty sady Office](../vsto/windows-forms-controls-on-office-documents-overview.md)|Popisuje, jak můžete přidat ovládací prvky Windows Forms na listech aplikace Excel.|  
|[Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Excel](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)|Ukazuje, jak vytvořit základní přizpůsobení na úrovni dokumentu pro Excel.|  
|[Návod: Vytvoření vaší první Add-in VSTO pro Excel](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)|Ukazuje, jak vytvořit základní Add-in VSTO pro Excel.|  
|[Návod: Přidání ovládacích prvků na list za běhu v projektu doplňku VSTO](../vsto/walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project.md)|Demonstruje postup přidání tlačítka Windows Forms <xref:Microsoft.Office.Tools.Excel.NamedRange>a <xref:Microsoft.Office.Tools.Excel.ListObject> na list za běhu pomocí doplňku VSTO.|
|[Pochopení společné pro vytváření obsahu a doplňky](./understanding-coauthoring-and-addins.md)|Popisuje úpravy, které možná budete muset provést řešení pro přizpůsobení Backstage.|  
|[Excel 2010 v vývoj pro Office](http://go.microsoft.com/fwlink/?LinkId=199011)|Obsahuje odkazy na články a referenční dokumentaci o vývoji řešení pro aplikaci Excel. Tyto nejsou specifické pro vývoj pro Office pomocí sady Visual Studio.|  
  
  
---
title: Začínáme s programováním přizpůsobení na úrovni dokumentu pro Excel
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel solutions in Visual Studio
- Excel projects [Office development in Visual Studio], getting started
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a336463a3a7d8003c949242ad2f295a76633c894
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56603791"
---
# <a name="get-started-programming-document-level-customizations-for-excel"></a>Začínáme s programováním přizpůsobení na úrovni dokumentu pro Excel
  Pokud jste začali vytvářet přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Excel s použitím sady Visual Studio, zde je, co potřebujete vědět.

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

## <a name="understand-how-document-level-customizations-for-excel-work"></a>Vysvětlení přizpůsobení na úrovni dokumentu pro Excel práce
 Přizpůsobení úrovni dokumentu pro Excel je podle jednoho sešitu. Pokud chcete začít používat vlastní nastavení, koncový uživatel otevře sešit nebo vytvoří sešitu z šablony aplikace Excel. Události v sešitu, třeba zadáním do buňky nebo kliknutím na tlačítka a položky nabídky, může volat metody zpracování událostí v sestavení. Při zavření sešitu funkcí poskytovaných službou přizpůsobení již nejsou k dispozici v aplikaci Excel, pouze v dokumentu, který je obsažen.

 Další informace najdete v tématu [architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md).

## <a name="create-document-level-projects-for-excel"></a>Vytvořit projekty na úrovni dokumentu pro Excel
 K vytvoření přizpůsobení na úrovni dokumentu pro Excel, použijte šablonu projektu Excelového sešitu nebo šabloně aplikace Excel v **nový projekt** dialogové okno. Tyto šablony zahrnují odkazy na požadovaná sestavení a soubory projektu.

 Další informace o tom, jak vytvořit projekt úrovni dokumentu pro Excel najdete v tématu [jak: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md). Další informace o šablonách projektů, naleznete v tématu [Přehled šablon projektů Office project](../vsto/office-project-templates-overview.md).

## <a name="program-excel-workbooks-by-using-host-items-and-host-controls"></a>Program Excelové sešity pomocí hostitelských položek a hostitelských ovládacích prvků
 *Hostování položky* a *hostování ovládacích prvků* jsou třídy, které poskytují programovací model pro přizpůsobení na úrovni dokumentu vytvořené pomocí sady Visual Studio.

 Hostitelské položky poskytují vstupní bod pro kód a mohou chovat i jako kontejnery pro hostitelské ovládací prvky a ovládací prvky Windows Forms. V projektech na úrovni dokumentu pro Excel, jsou reprezentovány tyto položky hostitele `ThisWorkbook`, `Sheet1`, `Sheet2`, a `Sheet3` třídy.

 Hostitelské ovládací prvky jsou založeny na nativních objektů aplikace Excel, jako je například seznam objektů a rozsahy adres. Hostitelské ovládací prvky poskytují podobné funkce jako nativní objektů aplikace Excel, ale mají také nové události, podpora návrháře a datové vazby funkce. Zobrazí se jako první třídy objektů ve vašem kódu projektu a v technologii IntelliSense, která usnadňuje odkazovat na konkrétní objekty přímo v kódu bez nutnosti procházení modelu objektů aplikace Excel.

 Další informace naleznete v následujících tématech:

-   [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)

-   [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)

-   [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)

## <a name="customize-the-user-interface-of-excel"></a>Přizpůsobení uživatelského rozhraní aplikace Excel
 Většina řešení Microsoft Office upravit uživatelské rozhraní (UI) aplikace Office kvůli nějakému uživatelům interakci s řešením. Existuje mnoho způsobů, jimiž lze upravit uživatelské rozhraní Excelu pomocí přizpůsobení úrovni dokumentu. Například můžete přidat ovládací prvky na pás karet, nebo můžete zobrazit podokna akcí. Další informace najdete v tématu [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).

 Můžete také otevřít sešit, který je přidružený k projektu přímo v sadě Visual Studio. Pokud se sešit otevřít v sadě Visual Studio, můžete upravit sešit s použitím uživatelského rozhraní aplikace Excel. Sešit můžete použít také jako návrhové ploše, která umožňuje přetažením ovládacích prvků na listech. Další informace najdete v tématu [projektech pro systém Office v prostředí sady Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md).

## <a name="use-data-binding"></a>Použití datových vazeb
 Hostitelské ovládací prvky jsou také v seznamu ovládacích prvků, které můžete přetáhnout z **zdroje dat** okna. Přidání hostitelské ovládací prvky v tomto způsobem automaticky váže je ke zdroji dat, které jste nastavili pomocí okna. Bez psaní kódu, můžete zobrazit data z databází, webových služeb a objektů firmy. Další informace najdete v tématu [vytvoření vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).

## <a name="next-steps"></a>Další kroky
 Informace o vytváření přizpůsobení na úrovni dokumentu pro Excel, naleznete v tématu [názorný postup: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Excel](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md). Tento návod vás seznámí s vývojářské nástroje balíku Office v sadě Visual Studio a programovací model pro přizpůsobení na úrovni dokumentu aplikace Excel.

 Seznam témat, která vás provede některé běžné úlohy v projektech aplikace Excel najdete v tématu [běžné úlohy při programování pro Office](../vsto/common-tasks-in-office-programming.md).

## <a name="see-also"></a>Viz také:
- [Postupy: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)
- [Řešení pro aplikaci Excel](../vsto/excel-solutions.md)
- [Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Excel](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)
- [Návody pro aplikaci Excel](../vsto/walkthroughs-using-excel.md)
- [Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)
- [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)

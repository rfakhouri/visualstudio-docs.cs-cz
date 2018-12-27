---
title: Začínáme s programováním přizpůsobení na úrovni dokumentu pro Word
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word solutions in Visual Studio
- Word projects [Office development in Visual Studio], getting started
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 36eedad9432738119b1993ba56ae46a363b166a0
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53648410"
---
# <a name="get-started-programming-document-level-customizations-for-word"></a>Začínáme s programováním přizpůsobení na úrovni dokumentu pro Word
  Pokud jste začali vytvářet přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Word s použitím sady Visual Studio, zde je, co potřebujete vědět.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
## <a name="understand-how-document-level-customizations-for-word-work"></a>Vysvětlení přizpůsobení na úrovni dokumentu pro Word práce  
 Každé slovo přizpůsobení, které vytvoříte vychází kolem jednotlivý dokument. Pokud chcete začít používat vlastní nastavení, koncový uživatel otevře dokument nebo vytvoří dokument z šablony aplikace Word. Události v dokumentu, třeba přesunutí kurzoru na konkrétní oblasti nebo kliknutím na tlačítka a položky nabídky, může volat metody zpracování událostí v sestavení. Při zavření dokumentu funkcí poskytovaných službou přizpůsobení již nejsou k dispozici v aplikaci Word.  
  
 Další informace najdete v tématu [architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md).  
  
## <a name="create-document-level-projects-for-word"></a>Vytvořit projekty na úrovni dokumentu pro aplikaci Word  
 K vytvoření přizpůsobení na úrovni dokumentu pro Word, použijte šablonu projektu dokumentu aplikace Word a šablona aplikace Word v **nový projekt** dialogové okno. Tyto šablony zahrnují odkazy na požadovaná sestavení a soubory projektu.  
  
 Další informace o tom, jak vytvořit projekt úrovni dokumentu pro aplikaci Word, najdete v části [jak: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md). Další informace o šablonách projektů, naleznete v tématu [Přehled šablon projektů Office project](../vsto/office-project-templates-overview.md).  
  
## <a name="program-word-documents-by-using-host-items-host-controls"></a>Hostování ovládacích prvků programu dokumentů aplikace Word s použitím hostitelské položky  
 *Hostování položky* a *hostování ovládacích prvků* jsou třídy, které poskytují programovací model pro přizpůsobení na úrovni dokumentu.  
  
 Hostitelské položky poskytují vstupní bod pro kód a mohou chovat i jako kontejnery pro hostitelské ovládací prvky a ovládací prvky Windows Forms. V projektech na úrovni dokumentu pro aplikaci Word, je reprezentována položka hostitele `ThisDocument` třídy.  
  
 Hostitelské ovládací prvky jsou založeny na nativních objektů aplikace Word, jako je například ovládací prvky obsahu, záložek a z uzlů XML. Hostitelské ovládací prvky poskytují podobné funkce jako nativní objekty aplikace Word, ale mají také nové události, podpora návrháře a datové vazby funkce. Zobrazí se jako první třídy objektů ve vašem kódu projektu a v technologii IntelliSense, která usnadňuje odkazovat na konkrétní objekty přímo v kódu bez nutnosti přechodu objektovému modelu Wordu.  
  
 Další informace naleznete v následujících tématech:  
  
-   [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)  
  
-   [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)  
  
-   [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)  
  
## <a name="customize-the-user-interface-of-word"></a>Přizpůsobení uživatelského rozhraní aplikace Word  
 Většina řešení Microsoft Office upravit uživatelské rozhraní (UI) aplikace Office kvůli nějakému uživatelům interakci s řešením. Existuje mnoho způsobů, jimiž můžete upravit uživatelského rozhraní aplikace Word s použitím přizpůsobení úrovni dokumentu. Například můžete přidat ovládací prvky na pás karet, a můžete zobrazit podokna akcí. Další informace najdete v tématu [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
 Můžete také otevřít dokument, který je přidružený k projektu přímo v sadě Visual Studio. Pokud dokument je otevřen v sadě Visual Studio, můžete upravit dokumentu pomocí uživatelského rozhraní aplikace Word. Dokument můžete použít také jako návrhové ploše, která umožňuje přetažením ovládacích prvků. Další informace najdete v tématu [projektech pro systém Office v prostředí sady Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
## <a name="bind-controls-to-data"></a>Vytvoření vazby ovládacích prvků k datům  
 Ovládací prvky obsahu a <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku se v seznamu ovládacích prvků, které můžete přetáhnout z **zdroje dat** okna. Přidání obsahu ovládací prvky a záložky v tomto způsobem automaticky váže je ke zdroji dat, které jste nastavili pomocí okna. Bez psaní kódu, můžete zobrazit data z databází, služeb a pro obchodní objekty. Další informace najdete v tématu [vytvoření vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
## <a name="next-steps"></a>Další kroky  
 Zjistěte, jak vytvořit přizpůsobení úrovni dokumentu pro aplikaci Word, najdete v článku [názorný postup: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md). Tento návod vás seznámí s vývojářské nástroje balíku Office v sadě Visual Studio a programovací model pro přizpůsobení na úrovni dokumentu aplikace Word.  
  
 Seznam témat, které vás provedou některé běžné úlohy v projektech aplikace Word, najdete v části [běžné úlohy při programování pro Office](../vsto/common-tasks-in-office-programming.md).  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Řešení aplikace Word](../vsto/word-solutions.md)   
 [Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)   
 [Návody pro aplikaci Word](../vsto/walkthroughs-using-word.md)   
 [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)  
  
  
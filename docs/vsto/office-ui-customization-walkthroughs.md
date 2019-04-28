---
title: Návody pro přizpůsobení uživatelského rozhraní Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- actions panes, walkthroughs
- smart documents, walkthroughs
- walkthroughs [Office development in Visual Studio], smart tags
- walkthroughs [Office development in Visual Studio], action panes
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 95561f1404da1efd71ff3418f9154392f393795c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977884"
---
# <a name="office-ui-customization-walkthroughs"></a>Návody pro přizpůsobení uživatelského rozhraní Office
  Následující postupy ukazují, že se způsoby, které lze přizpůsobit uživatelské rozhraní (UI) aplikace Microsoft Office s použitím přizpůsobení na úrovni dokumentu a doplňky VSTO.

## <a name="actions-pane-walkthroughs"></a>Návody pro podokna akcí
- [Návod: Vkládání textu do dokumentu z podokna akcí](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md) ukazuje, jak vytvořit podokna akcí ve Wordovém dokumentu. V podokně Akce obsahuje dva ovládací prvky, které odesílají vstupu uživatele pro dokument.

- [Návod: Vytvoření vazby dat s ovládacími prvky v podokně akcí aplikace Word](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md) ukazuje, jak svázat ovládací prvky v podokně akcí ve Wordu k datům. Ovládací prvky ukazují záznamů master/detail relace mezi tabulkami v databázi serveru SQL Server.

- [Návod: Vytvoření vazby dat k ovládacím prvkům v podokně akcí aplikace Excel](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md) popisuje, jak přidat ovládací prvky, které jsou vázány na zdroj dat do podokna akcí v aplikaci Excel.

## <a name="custom-task-pane-walkthroughs"></a>Návody pro podokno úloh
- [Návod: Automatizace aplikace z vlastního podokna úloh](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md) ukazuje, jak vytvořit vlastního podokna úloh, která obsahuje ovládací prvek, který automatizuje hostitelská aplikace, když uživatel klikne ovládací prvek.

- [Návod: Synchronizace vlastního podokna úloh s tlačítkem pásu karet](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md) ukazuje, jak vytvořit vlastního podokna úloh, které uživatelé můžou skrýt nebo zobrazit kliknutím na přepínací tlačítko na pásu karet.

- [Návod: Zobrazení vlastních podoken úloh s e-mailové zprávy v aplikaci Outlook](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md) ukazuje, jak zobrazit jedinečnou instanci vlastního podokna úloh s každou e-mailové zprávy, který je vytvořen nebo otevřen v aplikaci Outlook.

## <a name="ribbon-walkthroughs"></a>Návody pro pás karet
- [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md) ukazuje, jak vytvořit vlastní pásu karet pomocí Návrháře pásu karet. Na kartě obsahuje tlačítko, které lze použít pro skrytí nebo zobrazení podokna akcí.

- [Návod: Aktualizace ovládacích prvků na pásu karet za běhu](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md) demonstruje použití objektového modelu pásu karet po načtení pásu do aplikace sady Office aktualizace ovládacích prvků na pásu karet.

- [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md) ukazuje, jak vytvořit vlastní pásu karet pomocí kódu XML pásu karet namísto použití Návrháře pásu karet.

## <a name="controls-on-word-documents"></a>Ovládací prvky v dokumentech aplikace Word
- [Návod: Přidání ovládacích prvků do dokumentu za běhu v doplňku VSTO](../vsto/walkthrough-adding-controls-to-a-document-at-run-time-in-a-vsto-add-in.md) ukazuje, jak přidat ovládací prvky do dokumentu pomocí doplňku VSTO.

- [Návod: Změna formátování dokumentů s použitím ovládacích prvků CheckBox](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md) ukazuje, jak se změna formátování pomocí zaškrtávacích políček v přizpůsobení na úrovni dokumentu dokument aplikace Word.

- [Návod: Zobrazení textu v textovém poli v dokumentu s použitím tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md) ukazuje, jak pomocí tlačítka a textová pole v dokumentech aplikace Word.

- [Návod: Aktualizace grafu v dokumentu s použitím přepínačů](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md) ukazuje, jak změnit styly grafu ve Wordovém dokumentu pomocí tlačítek možností v přizpůsobení na úrovni dokumentu.

## <a name="controls-on-excel-worksheets"></a>Ovládacích prvků na listech aplikace Excel
- [Návod: Přidání ovládacích prvků na list za běhu v projektu doplňku VSTO](../vsto/walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project.md) ukazuje, jak přidat ovládací prvky do listu pomocí doplňku VSTO.

- [Návod: Změna formátování listů s použitím ovládacích prvků CheckBox](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md) ukazuje základy používání zaškrtávacích políček na listu aplikace Excel Změna formátování.

- [Návod: Zobrazení textu v textovém poli na listu s použitím tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md) ukazuje základy používání tlačítka a textová pole na listech aplikace Excel.

- [Návod: Aktualizace grafu na listu s použitím přepínačů](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md) ukazuje základy změna stylů grafu na listu aplikace Excel pomocí přepínače.

## <a name="see-also"></a>Viz také:
- [Návody pro aplikaci Word](../vsto/walkthroughs-using-word.md)
- [Návody pro aplikaci Excel](../vsto/walkthroughs-using-excel.md)
- [Data v návody pro řešení Office](../vsto/data-in-office-solutions-walkthroughs.md)
- [Návody pro zabezpečení a nasazení](../vsto/security-and-deployment-walkthroughs.md)
- [Začínáme &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Běžné úlohy při programování pro systém Office](../vsto/common-tasks-in-office-programming.md)
- [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)

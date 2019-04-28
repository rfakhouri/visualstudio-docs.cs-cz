---
title: 'Postupy: Export pásu karet z Návrháře pásu karet do kódu XML pásu karet'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, XML
- customizing the Ribbon, XML
- Ribbon [Office development in Visual Studio], XML
- Ribbon [Office development in Visual Studio], exporting
- XML [Office development in Visual Studio], Ribbon
- Ribbon Designer [Office development in Visual Studio]
- exporting Ribbon
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 17d6efe4aa18682c6777128113f6fa60347f8950
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63419494"
---
# <a name="how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Postupy: Export pásu karet z Návrháře pásu karet do kódu XML pásu karet
  **Pás karet (vizuální návrhář)** položka nepodporuje všechny možné typy vlastního nastavení pásu karet. Přizpůsobení pásu karet v upřesňující možnosti, můžete exportovat do kódu XML pásu karet na pásu karet z návrháře a přímo upravit soubor XML.

> [!NOTE]
> Zobrazí všechny hodnoty vlastností v souboru XML pásu karet. Další informace najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Export pásu karet z Návrháře pásu karet do kódu XML pásu karet

1. Klikněte pravým tlačítkem na soubor kódu pásu karet v **Průzkumníka řešení**a potom klikněte na tlačítko **Návrhář zobrazení**.

2. Klikněte pravým tlačítkem na Návrhář pásu karet a potom klikněte na tlačítko **Export pásu karet do XML**.

     Visual Studio přidá souboru XML pásu karet a soubor kódu XML pásu karet do projektu.

3. Ve třídě pásu karet kódu vyhledejte komentáře, které začínají `TODO:`.

4. Zkopírujte blok kódu do těchto komentářů k **ThisAddin**, **ThisWorkbook**, nebo **ThisDocument** třídy, v závislosti na tom, jaký typ řešení, kterou vyvíjíte.

     Tento kód povoluje aplikace Microsoft Office zjišťovat a načíst vaše vlastní pás karet. Další informace najdete v tématu [kódu XML pásu karet](../vsto/ribbon-xml.md).

5. V **ThisAddin**, **ThisWorkbook**, nebo **ThisDocument** třídy, zrušte komentář u bloku kódu.

     Po zrušte komentář u kód by měl vypadat podobně jako v následujícím příkladu. V tomto příkladu se nazývá třídě pásu karet `MyRibbon`.

     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]

6. Přejděte do souboru kódu XML pásu karet a najít `Ribbon Callbacks` oblasti.

     Toto je místo, kde píšete metody zpětného volání pro zpracování uživatelské akce, jako je kliknutí na tlačítko.

7. Vytvořte metody zpětného volání pro každou obslužnou rutinu události, kterou jste napsali v kódu Návrháře pásu karet.

8. Přesunout všechny svůj kód obslužné rutiny události z obslužné rutiny události do metod zpětného volání a upravte kód pro práci s pásu karet ribbonx (Ribbon extensibility) programovacího modelu.

     Informace o psaní metody zpětného volání a pomocí programovacího modelu Ribbon najdete v tématu [kódu XML pásu karet](../vsto/ribbon-xml.md).

## <a name="see-also"></a>Viz také:
- [Přehled pásu karet](../vsto/ribbon-overview.md)
- [Návrhář pásu karet](../vsto/ribbon-designer.md)
- [Pás karet – XML](../vsto/ribbon-xml.md)
- [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)

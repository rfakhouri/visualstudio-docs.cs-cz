---
title: Přehled šablon projektů Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- templates [Office development in Visual Studio], about project templates
- Excel Workbook project template
- Word Template project template
- Excel [Office development in Visual Studio], project templates
- Project [Office development in Visual Studio], project templates
- project templates [Office development in Visual Studio]
- project templates, Word
- InfoPath [Office development in Visual Studio], project templates
- Excel Template project template
- project templates, 2007 Microsoft Office system
- project templates, Excel
- PowerPoint [Office development in Visual Studio], project templates
- Word [Office development in Visual Studio], Word project templates
- Office projects [Office development in Visual Studio], templates
- Excel projects in Visual Studio
- Word Document project template
- Visio [Office development in Visual Studio], project templates
- Word projects in Visual Studio
- Outlook [Office development in Visual Studio], project templates
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d83b04795386cfec80a8a309a9a84da04f6df105
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926592"
---
# <a name="office-project-templates-overview"></a>Přehled šablon projektů Office
  Nástroje systém Microsoft Office Developer Tools v sadě Visual Studio obsahují šablony projektů pro vytváření následujících typů řešení pro systém Office:

- [Přizpůsobení na úrovni dokumentu](#DocLevel)

- [Doplňky VSTO](#AppLevel)

  Podrobné porovnání těchto typů řešení pro Office najdete v tématu [Přehled &#40;vývoje řešení pro systém Office VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).

  Šablony projektu Office jsou k dispozici v dialogovém okně **Nový projekt** v části uzel **Office** v uzlech **Visual C#**  a **Visual Basic** jazyka. Každá šablona generuje projekt s odpovídající konfigurací pro cílovou aplikaci, včetně odkazů na sestavení a nastavení ladění.

  Každý projekt obsahuje soubory a kód umožňující začít pracovat na konkrétním typu řešení. Vygenerovaný kód pro každý projekt obsahuje obslužné rutiny událostí spuštění a ukončení. Do těchto obslužných rutin událostí můžete přidat kód pro inicializaci vašeho řešení při spuštění a pro vyčištění při jeho uvolnění z paměti. Další informace najdete v tématu [projekty Office v prostředí sady Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md) a [v tématu události v projektech Office](../vsto/events-in-office-projects.md).

> [!NOTE]
> Nástroje pro vývoj pro Office jsou součástí určitých edicí sady Visual Studio. Další informace najdete v tématu [Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/configuring-a-computer-to-develop-office-solutions.md).

## <a name="DocLevel"></a>Přizpůsobení na úrovni dokumentu
 Uzel **Office** v dialogovém okně **Nový projekt** poskytuje následující šablony projektu, které vám pomohou začít vytvářet přizpůsobení na úrovni dokumentu pro Word a Excel:

- **Dokument aplikace Word 2013 a 2016 VSTO**

- **Šablona VSTO pro Word 2013 a 2016**

- **Sešit VSTO pro Excel 2013 a 2016**

- **Šablona VSTO pro Excel 2013 a 2016**

- **Dokument VSTO pro Word 2010**

- **Šablona VSTO pro Word 2010**

- **Sešit VSTO pro Excel 2010**

- **Šablona VSTO pro Excel 2010**

  Šablony projektů Dokument aplikace Word a Sešit aplikace Excel poskytují kód, pomocí něhož můžete začít vytvářet řešení založené na konkrétním dokumentu nebo sešitu. V těchto typech řešení je váš kód spuštěn, pouze když je přidružený dokument otevřen v aplikaci Word nebo Excel.

  Šablony projektů Šablona aplikace Word a Šablona aplikace Excel se chovají stejně jako šablony projektů Dokument aplikace Word a Sešit aplikace Excel. Šablony projektů Šablona aplikace Word a Šablona aplikace Excel ale usnadňují uživatelům vytvoření nových místních kopií dokumentu nebo sešitu pomocí přizpůsobené šablony z vašeho řešení. Funkce vašeho řešení jsou k dispozici z nového dokumentu, který uživatel z šablony vytvoří.

> [!NOTE]
> Šablony aplikace Word, které odkazují na rozšíření spravovaného kódu, se nedají použít jako globální doplňky VSTO. Sestavení není voláno, pokud je šablona načtena z adresáře Po spuštění aplikace Word. Další informace najdete v tématu [omezení globálních šablon a doplňků aplikace Excel (soubory. xla)](#Limitations).

 Informace, jak začít pracovat s těmito typy projektů, naleznete v následujících tématech:

- [Přizpůsobení na úrovni dokumentu programu](../vsto/programming-document-level-customizations.md)

- [Řešení pro Word](../vsto/word-solutions.md)

- [Řešení pro Excel](../vsto/excel-solutions.md)

- [Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Word](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)

- [Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Excel](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)

## <a name="AppLevel"></a>Doplňky VSTO
 Uzel **Office/SharePoint** v dialogovém okně **Nový projekt** poskytuje následující šablony projektu, které vám pomohou začít vytvářet doplňky VSTO.

- **Doplněk VSTO pro Excel 2013 a 2016**

- **Doplněk VSTO pro InfoPath 2013**

- **Doplněk VSTO pro Outlook 2013 a 2016**

- **Doplněk pro PowerPoint 2013 a 2016**

- **Doplněk pro Project 2013 a 2016**

- **Doplněk Visia 2013 a 2016**

- **Doplněk pro Word 2013 a 2016**

- **Doplněk pro Excel 2010**

- **Doplněk InfoPath 2010**

- **Doplněk pro Outlook 2010**

- **Doplněk pro PowerPoint 2010**

- **Doplněk pro Project 2010**

- **Doplněk pro Visio 2010**

- **Doplněk pro Word 2010**

  Když vytvoříte projekt, který je založen na jedné z těchto šablon projektů, je kód ve vašem řešení spuštěn při spuštění přidružené aplikace. Na rozdíl od projektů na úrovni dokumentu není váš kód přidružen k jednomu dokumentu.

  Další informace o tom, jak začít pracovat s těmito typy projektů, naleznete v následujících tématech:

- [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)

- [Programové doplňky VSTO](../vsto/programming-vsto-add-ins.md)

- [Návod: Vytvoření prvního doplňku VSTO pro Excel](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)

- [Návod: Vytvoření prvního doplňku VSTO pro Outlook](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)

- [Návod: Vytvoření prvního doplňku VSTO pro PowerPoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)

- [Návod: Vytvoření prvního doplňku VSTO pro Project](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)

- [Návod: Vytvoření prvního doplňku VSTO pro Word](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)

## <a name="document-vs-template-solutions"></a>Řešení dokumentů a šablon
 Při návrhu řešení, které je založeno na dokumentu aplikace Word nebo sešitu aplikace Excel, se musíte rozhodnout, jak nejlépe zpřístupnit tento dokument uživateli.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 V některých situacích může být vhodné poskytnout každému uživateli kopii dokumentu. V takovém případě vytvořte řešení pomocí projektu dokumentu aplikace Excel nebo Word.

 V jiných situacích může být vhodné zpřístupnit šablonu na serveru, aby si každý uživatel mohl šablonu otevřít a uložit si místní kopii dokumentu. V takovém případě vytvořte řešení pomocí projektu šablony aplikace Excel nebo Word.

## <a name="comparison"></a>Srovnání
 Následující tabulka popisuje rozdíly mezi dokumenty a šablonami.

|Dokumenty|Šablony|
|---------------|---------------|
|Uživatelé mohou dokument otevřít a upravit, pokud není nastaven jen pro čtení. Jakékoli uložené změny se uchovávají v originálu dokumentu.|Uživatelé mohou šablonu otevřít a vytvořit pomocí ní místní kopii jako nový dokument. Nemohou originál upravovat, pokud jim neudělíte speciální oprávnění.|
|Po otevření dokument vyvolá <xref:Microsoft.Office.Tools.Word.Document.Open> událost.|Po otevření šablona vyvolá <xref:Microsoft.Office.Tools.Word.Document.New> událost.|

## <a name="Limitations"></a>Omezení globálních šablon a doplňků aplikace Excel (soubory. xla)
 Dokumenty, sešity a šablony nemusí fungovat správně jako globální šablony nebo doplňky Excel VSTO (soubory. xla).

## <a name="word-templates"></a>Šablony aplikace Word
 Pokud má šablona aplikace Microsoft Office Word rozšíření se spravovaným kódem, není voláno sestavení projektu, pokud je šablona připojena jako globální šablona nebo načtena z adresáře Po spuštění aplikace Word. Dokument navíc nerozpozná formát šablony, která je součástí řešení pro Office.

## <a name="excel-add-ins-xla-files"></a>Excelové doplňky (soubory. xla)
 Není k dispozici žádný projekt Office pro vytvoření doplňku VSTO pro Excel (soubor *. xla* ). Je možné uložit sešit jako soubor s příponou .xla, ale tato operace není podporována ani doporučena. Pokud uložíte sešit, který má rozšíření spravovaného kódu jako **systém Microsoft Office excelový soubor doplňku (\*. xla)** , můžete ho vybrat v dialogovém okně **Doplňky** a použít ho na jiný sešit. V některých případech se váš kód spustí v cílovém sešitu po použití doplňku VSTO, ale toto použití řešení Office se nepodporuje.

## <a name="see-also"></a>Viz také:
- [Návrh a tvorba řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)
- [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)
- [Postupy: Vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Začínáme s programováním přizpůsobení na úrovni dokumentu pro Excel](../vsto/getting-started-programming-document-level-customizations-for-excel.md)
- [Začínáme programovat přizpůsobení na úrovni dokumentu pro Word](../vsto/getting-started-programming-document-level-customizations-for-word.md)
- [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)

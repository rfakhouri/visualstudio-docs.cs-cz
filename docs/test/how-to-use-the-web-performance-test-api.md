---
title: Webové rozhraní API testu výkonnosti v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, using the API
- APIs, Web performance tests
ms.assetid: 93a6a1dd-663b-4ab5-8760-7d6b081561d3
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: ed7cbc7375cbf416d82a56c140479925569dad8d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-the-web-performance-test-api"></a>Postupy: Použití rozhraní API testu výkonnosti webu

Můžete napsat kód pro vaše testy výkonnosti webu. Testu výkonnosti webu, které rozhraní API slouží k vytvoření programových testy výkonnosti webu, testovací zásuvné moduly výkonu webového, žádost moduly plug-in, požadavků, pravidla pro extrakci a pravidla ověřování. Třídy, které tvoří tyto typy jsou základní třídy v tomto rozhraní API. Jiné typy v tomto rozhraní API slouží k podpoře vytváření <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTest>, <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>, <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>, <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequest>, <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule>, a <xref:Microsoft.VisualStudio.TestTools.WebTesting.ValidationRule> objekty. Můžete použít <xref:Microsoft.VisualStudio.TestTools.WebTesting> obor názvů pro vytvoření přizpůsobené testy výkonnosti webu.

 Můžete také Web API testu výkonu prostřednictvím kódu programu vytvoříte a uložíte deklarativní testy výkonnosti webu. Chcete-li to provést, použijte <xref:Microsoft.VisualStudio.TestTools.WebTesting.DeclarativeWebTest> a <xref:Microsoft.VisualStudio.TestTools.WebTesting.DeclarativeWebTestSerializer> třídy.

> [!TIP]
>  Kontrola pomocí prohlížeče objektů <xref:Microsoft.VisualStudio.TestTools.WebTesting> oboru názvů. Editory jak Visual C# a Visual Basic nabízí podporu technologie IntelliSense pro psaní kódu s použitím třídy v oboru názvů.

 Můžete také vytvořit modulů Plugin pro zátěžové testy. Další informace najdete v tématu [postupy: použití rozhraní API testu zatížení](../test/how-to-use-the-load-test-api.md) a [postupy: vytvoření modulu Plugin pro Test zatížení](../test/how-to-create-a-load-test-plug-in.md).

## <a name="to-use-the-webtesting-namespace"></a>Pro používání oboru názvů WebTesting

1.  Otevřete projekt testu výkonnosti webu a zátěžového testu, který obsahuje test výkonnosti webu.

2.  Přidejte Visual C# nebo Visual Basic projektu knihovny tříd do řešení pro test.

3.  Přidejte odkaz na projekt knihovny tříd ve webovém projektu test výkonu a zatížení.

4.  Přidejte odkaz na knihovnu DLL Microsoft.VisualStudio.QualityTools.WebTestFramework v projektu knihovny tříd.

5.  V souboru třídy, který je umístěný v projektu knihovny tříd, přidejte `using` údajů <xref:Microsoft.VisualStudio.TestTools.WebTesting> obor názvů.

6.  Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin> rozhraní.

7.  Sestavte projekt.

8.  Přidání nového testu výkonnosti webu modulu plug-in pomocí Editor testů výkonnosti webu:

    1.  Zvolte **přidat zásuvný modul testu Web** na panelu nástrojů.

         **Přidat zásuvný modul testu Web** se zobrazí dialogové okno.

    2.  V části **vyberte modul plug-in**vyberte výkon vašich webových testů modulu plug-in třídy.

    3.  V **vlastnosti pro vybraný modul plug-in** podokně nastavit počáteční hodnoty pro modul plug-in pro použití v době běhu.

        > [!NOTE]
        > Z modulu plug-in lze vystavit libovolný počet vlastností, ale je třeba je nastavit jako veřejné a nastavitelné a musí mít základní typ, jako je například Integer, Boolean nebo String. Můžete také upravit vlastnosti modulu plug-in test výkonu webové později pomocí okna Vlastnosti.

    4.  Zvolte **OK**.

9. Spusťte test výkonnosti webu.

     Pro příklad implementace <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>, najdete v části [postupy: vytvoření zásuvný modul testu výkonu Web](../test/how-to-create-a-web-performance-test-plug-in.md).

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.WebTesting>
- [Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Postupy: použití rozhraní API zátěžového testu](../test/how-to-use-the-load-test-api.md)
- [Postupy: vytvoření modulu Plugin pro Test výkonnosti webu](../test/how-to-create-a-web-performance-test-plug-in.md)
---
title: Zátěžový Test rozhraní API v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- code, load tests
- plug-ins, load test
- APIs, load tests
ms.assetid: e15567bc-1f21-4feb-b81d-f17ba35cfde5
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 3a5204848c24a25514fc8eb30a81dbca704a77a3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-the-load-test-api"></a>Postupy: Použití rozhraní API zátěžového testu

Visual Studio podporuje zatížení testovací moduly plug-in, které můžete řídit nebo vylepšují zátěžový test. Zásuvné moduly testu zatížení jsou uživatelsky definované třídy, které implementují rozhraní <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> rozhraní v nalezen <xref:Microsoft.VisualStudio.TestTools.LoadTesting> obor názvů. Zásuvné moduly testu zatížení umožňují vlastní zatížení testovací kontrolu, jako je třeba při splnění prahové hodnoty čítače nebo chyby přerušuje zátěžový test. Použít vlastnosti na <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest> třída pro získání nebo nastavení parametry testu zatížení od uživatele definována kódu. Použít na události <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest> třída připojit delegáty pro oznámení, když běží zátěžový test.

> [!TIP]
> Kontrola pomocí prohlížeče objektů <xref:Microsoft.VisualStudio.TestTools.LoadTesting> oboru názvů. Editory jak Visual C# a Visual Basic nabízí podporu technologie IntelliSense pro psaní kódu s použitím třídy v oboru názvů.

Lze také vytvořit moduly plug-in pro testy výkonnosti webu. Další informace najdete v tématu [postupy: vytvoření zásuvný modul testu výkonu Web](../test/how-to-create-a-web-performance-test-plug-in.md) a [postupy: vytvoření modulu Plugin úrovni požadavků](../test/how-to-create-a-request-level-plug-in.md).

## <a name="to-use-the-loadtesting-namespace"></a>Pro používání oboru názvů LoadTesting

1.  Otevřete výkon a zatížení testu webu projekt, který obsahuje zátěžový test.

2.  Přidejte Visual C# nebo Visual Basic projektu knihovny tříd do řešení pro test.

3.  Přidejte odkaz na projekt knihovny tříd ve webovém projektu test výkonu a zatížení.

4.  Přidejte odkaz na knihovnu DLL Microsoft.VisualStudio.QualityTools.LoadTestFramework v projektu knihovny tříd.

5.  V souboru třídy, který se nachází v projektu knihovny tříd, přidejte `using` údajů <xref:Microsoft.VisualStudio.TestTools.LoadTesting> oboru názvů.

6.  Vytvořte veřejný třídu, která implementuje <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> rozhraní.

7.  Sestavte projekt.

8.  Přidání nového modulu plug-in pomocí editoru načíst testování zátěžového testu:

    1.  Klikněte pravým tlačítkem na kořenový uzel testu zatížení a potom zvolte **přidat Plug-in načíst testování**.

    2.  **Přidat Plug-in testu zatížení** se zobrazí dialogové okno.

    3.  V dialogovém okně Vlastnosti pro vybraný modul plug-in podokně nastavte počáteční hodnoty pro modul plug-in pro použití v době běhu.

        > [!NOTE]
        > Můžete vystavit tolik vlastnosti tak, jak chcete z moduly plug-in. Se jich veřejné, nastavit a základní typ jako celé číslo, logická hodnota nebo řetězec. Můžete taky upravit vlastnosti modulu plug-in testu zatížení později pomocí okna Vlastnosti.

9. Spusťte zátěžový test.

     Implementace <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>, najdete v části [postupy: vytvoření modulu Plugin pro Test zatížení](../test/how-to-create-a-load-test-plug-in.md).

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.LoadTesting>
- [Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Postupy: použití rozhraní API testu výkonnosti webu](../test/how-to-use-the-web-performance-test-api.md)
- [Postupy: vytvoření modulu Plugin pro zátěžový Test](../test/how-to-create-a-load-test-plug-in.md)
---
title: Analýza programových testů uživatelského rozhraní pomocí protokolů z těchto testů v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 0c2ce02ddef992bc9b9bde56be699a097594ffae
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="analyzing-coded-ui-tests-using-coded-ui-test-logs"></a>Analýza programových testů uživatelského rozhraní pomocí protokolů z těchto testů

Programových filtru protokoly testu uživatelského rozhraní a záznam, který spouští důležité informace o vaší programového testu uživatelského rozhraní. Protokoly jsou uvedené ve formátu, který umožňuje rychle ladění problémů.

## <a name="step-1-enable-logging"></a>Krok 1: Povolení protokolování

V závislosti na scénáři Povolte protokol pomocí jedné z následujících metod:

- Cílové rozhraní .NET Framework verze 4 bez *App.config* souboru nacházejí v projektu testu:

   1. Otevřete **QTAgent32_40.exe.config** souboru. Ve výchozím nastavení je tento soubor umístěný ve *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

   2. Změňte hodnotu pro EqtTraceLevel na požadovanou úroveň protokolu.

   3. Uložte soubor.

- Cílové rozhraní .NET Framework verze 4.5 bez *App.config* souboru nacházejí v projektu testu:

   1. Otevřete **QTAgent32.exe.config** souboru. Ve výchozím nastavení je tento soubor umístěný ve *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

   2. Změníte hodnotu EqtTraceLevel na požadovanou úroveň protokolu.

   3. Uložte soubor.

- *App.config* souboru se nacházejí v projektu testu:

    - Otevřete *App.config* v projektu soubor a přidejte následující kód v uzlu Konfigurace:

      ```xml
      <system.diagnostics>
        <switches>
          <add name="EqtTraceLevel" value="4" />
        </switches>
      </system.diagnostics>`
      ```

- Povolte protokolování z samotný kód testu:

   <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.LoggerOverrideState%2A> = HtmlLoggerState.AllActionSnapshot;

## <a name="step-2-run-your-coded-ui-test-and-view-the-log"></a>Krok 2: Spuštění vaší programového testu uživatelského rozhraní a zobrazit protokol

Při spuštění programového testu uživatelského rozhraní se změny **QTAgent32.exe.config** soubor na místě, uvidíte výstup odkaz ve výsledcích testování Explorer. Soubory protokolu se produkují, ne jenom v případě, test nezdaří, ale i pro úspěšné testů, pokud je úroveň trasování nastavena na "verbose."

1.  Na **Test** nabídce zvolte **Windows** a pak vyberte **Průzkumníka testů**.

2.  Na **sestavení** nabídce zvolte **sestavit řešení**.

3.  V Průzkumníku testování vyberte programového testu UI chcete spouštět, otevřete jeho místní nabídce a potom zvolte **spuštění testů vyberte**.

     Automatizované testy spustit a pokud předaná nebo se nezdařilo.

    > [!TIP]
    > Chcete-li zobrazit Průzkumníka testů, zvolte **Test** > **Windows**a potom zvolte **Průzkumníka testů**.

4.  Vyberte **výstup** odkaz ve výsledcích Průzkumníka testů.

     ![Výstup odkaz v Průzkumníka testů](../test/media/cuit_htmlactionlog1.png "CUIT_HTMLActionLog1")

     Zobrazí se výstup pro test, který obsahuje odkaz na protokol akcí.

     ![Výsledky a odkazy na výstup z programového testu uživatelského rozhraní](../test/media/cuit_htmlactionlog2.png "CUIT_HTMLActionLog2")

5.  Vyberte *UITestActionLog.html* odkaz.

     Protokol se zobrazí ve webovém prohlížeči.

     ![Programové uživatelského rozhraní testovací soubor protokolu](../test/media/cuit_htmlactionlog3.png "CUIT_HTMLActionLog3")

## <a name="see-also"></a>Viz také

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Postupy: spouštění testů ze sady Microsoft Visual Studio](http://msdn.microsoft.com/Library/1a1207a9-2a33-4a1e-a1e3-ddf0181b1046)
---
title: Analýza programových testů uživatelského rozhraní pomocí protokolů z těchto testů
ms.date: 11/04/2016
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: a485f58e477d56625bc5ac88a014fc730057b97c
ms.sourcegitcommit: ba5e072c9fedeff625a1332f22dcf3644d019f51
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/31/2019
ms.locfileid: "66432305"
---
# <a name="analyzing-coded-ui-tests-using-coded-ui-test-logs"></a>Analýza kódované UI testy pomocí programového protokolů testu uživatelského rozhraní

Programového uživatelského rozhraní testu protokoly filtr a záznam, který běží důležité informace o programového testu UI. Protokoly jsou uvedeny ve formátu, který umožňuje ladění problémů rychle.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

## <a name="step-1-enable-logging"></a>Krok 1: Povolit protokolování

V závislosti na scénáři použijte jednu z následujících metod k povolení protokolu:

- Pokud není žádný *App.config* soubor v projektu testu:

   1. Určení, které *QTAgent\*.exe* proces se spustí při spuštění vašeho testu. Můžete provést například jde Přehrát **podrobnosti** karty ve Windows **Správce úloh**.
   
   2. Otevřete odpovídající *.config* soubor *% ProgramFiles (x86) %\Microsoft Visual Studio\\\<verze >\\\<edition > \Common7\IDE* složky. Například pokud proces, který spouští je *QTAgent_40.exe*, otevřete *QTAgent_40.exe.config*.

   2. Změnit hodnotu **EqtTraceLevel** na úroveň protokolu, který chcete.
   
      ```xml
      <!-- You must use integral values for "value".
           Use 0 for off, 1 for error, 2 for warn, 3 for info, and 4 for verbose. -->
      <add name="EqtTraceLevel" value="4" />
      ```

   3. Uložte soubor.

- Pokud dojde *App.config* soubor v projektu testu:

    - Otevřít *App.config* souboru v projektu a přidejte následující kód v uzlu Konfigurace:

      ```xml
      <system.diagnostics>
        <switches>
          <add name="EqtTraceLevel" value="4" />
        </switches>
      </system.diagnostics>`
      ```

- Povolení protokolování z samotný kód testu:

   ```csharp
   Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.LoggerOverrideState = HtmlLoggerState.AllActionSnapshot;
   ```

## <a name="step-2-run-your-coded-ui-test-and-view-the-log"></a>Krok 2: Spustit programový test uživatelského rozhraní a zobrazit protokol

Při spuštění programového testu uživatelského rozhraní pomocí změny *QTAgent\*. exe.config* soubor na místě, zobrazí se výstup na odkaz v **Průzkumníka testů** výsledky. Soubory protokolů jsou vytvářeny, nikoli pouze v případě test nepodaří ale také u úspěšných testů při úroveň trasování je nastavena na **podrobné**.

1. Na **testovací** nabídce zvolte **Windows** a pak vyberte **Průzkumník testů**.

2. Na **sestavení** nabídce zvolte **sestavit řešení**.

3. V **Průzkumníka testů**, vyberte programový test uživatelského rozhraní, kterou chcete spustit, otevřete místní nabídku a klikněte na tlačítko **spustit vyberte testy**.

     Automatizované testy proběhnou a označení pokud úspěšný nebo neúspěšný.

    > [!TIP]
    > Chcete-li zobrazit **Průzkumník testů**, zvolte **testovací** > **Windows**a klikněte na tlačítko **Průzkumník testů**.

4. Zvolte **výstup** odkaz v **Průzkumník testů** výsledky.

     ![Výstup odkaz v Průzkumníku testů](../test/media/cuit_htmlactionlog1.png)

     Zobrazí se výstup pro test, který obsahuje odkaz na protokol akcí.

     ![Výsledky a odkazy na výstup z programového testu uživatelského rozhraní](../test/media/cuit_htmlactionlog2.png)

5. Zvolte *UITestActionLog.html* odkaz.

     Protokol se zobrazí ve webovém prohlížeči.

     ![Programový soubor protokolu testu uživatelského rozhraní](../test/media/cuit_htmlactionlog3.png)

## <a name="see-also"></a>Viz také:

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Postupy: Spuštění testů ze sady Microsoft Visual Studio](https://msdn.microsoft.com/Library/1a1207a9-2a33-4a1e-a1e3-ddf0181b1046)

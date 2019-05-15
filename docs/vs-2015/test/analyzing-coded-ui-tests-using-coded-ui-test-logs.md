---
title: Analýza programových testů uživatelského rozhraní pomocí protokolů z těchto testů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 7e795873-1d4b-4a13-a52a-a411d87fb759
caps.latest.revision: 15
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7040b4dd07eebb4332634d5d8ffc1d9bc8d8c06b
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65686484"
---
# <a name="analyzing-coded-ui-tests-using-coded-ui-test-logs"></a>Analýza programových testů uživatelského rozhraní pomocí protokolů z těchto testů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Programového uživatelského rozhraní testu protokoly filtr a záznam, který běží důležité informace o programového testu UI.  
  
 **Požadavky**  
  
- Visual Studio Enterprise  
  
## <a name="why-should-i-do-this"></a>Proč to mám dělat?  
 Protokoly jsou uvedeny ve formátu, který umožňuje ladění problémů rychle.  
  
## <a name="how-do-i-do-this"></a>Jak to udělám?  
  
### <a name="step-1-enable-logging"></a>Krok 1: Povolit protokolování  
 V závislosti na scénáři použijte jednu z následujících metod k povolení protokolu.  
  
- Cílová verze rozhraní .NET Framework 4 s soubor App.config nacházejí v projektu testu  
  
    - Otevřít **QTAgent32_40.exe.config** souboru.  
  
         Ve výchozím nastavení je tento soubor umístěn ve  **\<drvie >: \Program soubory (x86) \Microsoft Visual Studio 12.0\Common7\IDE**.  
  
         Upravte hodnotu EqtTraceLevel na požadovanou úroveň protokolu.  
  
         Uložte soubor.  
  
- Cílová verze rozhraní .NET Framework 4.5 s soubor App.config nacházejí v projektu testu  
  
    - Otevřít **QTAgent32.exe.config** souboru.  
  
         Ve výchozím nastavení je tento soubor umístěn ve  **\<drvie >: \Program soubory (x86) \Microsoft Visual Studio 12.0\Common7\IDE**.  
  
         Upravte hodnotu EqtTraceLevel na požadovanou úroveň protokolu.  
  
         Uložte soubor.  
  
- K dispozici v testovacím projektu souboru app.config  
  
    - Otevřete soubor App.config v projektu.  
  
         Přidejte následující kód v uzlu Konfigurace:  
  
         `<system.diagnostics>     <switches>       <add name="EqtTraceLevel" value="4" />     </switches>  </system.diagnostics>`  
  
- Povolení protokolování z samotný kód testu  
  
    - <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.LoggerOverrideState%2A> = HtmlLoggerState.AllActionSnapshot;  
  
### <a name="step-2-run-your-coded-ui-test-and-view-the-log"></a>Krok 2: Spustit programový test uživatelského rozhraní a zobrazit protokol  
 Při spuštění programového testu uživatelského rozhraní pomocí změny **QTAgent32.exe.config** soubor na místě, se zobrazí ve výsledcích Průzkumníka testů není odkaz na výstup. Soubory protokolů jsou vytvářeny, ne jenom v případě, že se test nezdaří, ale také u úspěšných testů, pokud je úroveň trasování nastavena na "podrobné."  
  
1. Na **testovací** nabídce zvolte **Windows** a pak vyberte **Průzkumník testů**.  
  
2. Na **sestavení** nabídce zvolte **sestavit řešení**.  
  
3. V Průzkumníku testů vyberte programový test uživatelského rozhraní, kterou chcete spustit, otevřete místní nabídku a klikněte na tlačítko **spustit vyberte testy**.  
  
     Automatizované testy spustí a označení pokud úspěšný nebo neúspěšný.  
  
    > [!TIP]
    > Chcete-li zobrazit Průzkumník testování z **nabídka testu**, přejděte na **Windows** a klikněte na tlačítko **Průzkumník testů**.  
  
4. Zvolte **výstup** odkaz v Průzkumníku testů výsledky.  
  
     ![Výstup odkaz v Průzkumníku testů](../test/media/cuit-htmlactionlog1.png "CUIT_HTMLActionLog1")  
  
     Zobrazí se výstup testu, který bude obsahovat odkaz na protokol akcí.  
  
     ![Výsledky a odkazy na výstup z programového testu uživatelského rozhraní](../test/media/cuit-htmlactionlog2.png "CUIT_HTMLActionLog2")  
  
5. Zvolte odkaz UITestActionLog.html.  
  
     Protokol se zobrazí ve webovém prohlížeči.  
  
     ![Programových testů UI v souboru protokolu](../test/media/cuit-htmlactionlog3.png "CUIT_HTMLActionLog3")  
  
## <a name="q--a"></a>Dotazy a odpovědi  
  
### <a name="q-what-happened-to-the-enablehtmllogger-key"></a>DOTAZ: Co se stalo s klíči EnableHtmlLogger?  
 V předchozích verzích sady Visual Studio došlo k dvě další nastavení konfigurace pro povolení protokolování ve formátu Html v programový Test uživatelského rozhraní:  
  
```  
  
<add key="EnableHtmlLogger" value="true"/>  
  
<add key="EnableSnapshotInfo" value="true"/>  
  
```  
  
 Obě tato nastavení jsou zastaralé od verze Visual Studio 2012. EqtTraceLevel je pouze nastavení, které je potřeba upravit tak, aby povolit HtmlLogger.  
  
## <a name="see-also"></a>Viz také  
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
 [Postupy: Spuštění testů ze sady Microsoft Visual Studio](https://msdn.microsoft.com/library/1a1207a9-2a33-4a1e-a1e3-ddf0181b1046)

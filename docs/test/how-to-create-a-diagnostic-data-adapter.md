---
title: 'Postupy: vytvoření adaptéru diagnostických dat v sadě Visual Studio'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, creating
ms.assetid: bd7ad36c-54cb-4d2a-9aea-9d10ad98d7ba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 44d25ffee531c7b18240dcc65272d25bcb9e3402
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-diagnostic-data-adapter"></a>Postupy: Vytvoření adaptéru diagnostických dat

Chcete-li vytvořit *adaptér diagnostických dat*, vytvoření knihovny tříd pomocí sady Visual Studio a poté přidejte diagnostických dat adaptéru rozhraní API poskytované Visual Studio Enterprise knihovny tříd. Veškeré informace, které chcete používat jako datový proud nebo soubor, který chcete odeslat <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink> poskytuje rozhraní, při zpracování události, které jsou vyvolány během spuštění testu. Datové proudy nebo soubory odeslané <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink> jsou uloženy jako přílohy výsledků testů, až se dokončí test. Pokud vytvoříte chyby z nich testování výsledků nebo při použití [!INCLUDE[mtrlong](../test/includes/mtrlong_md.md)], soubory jsou také propojit k chybě.

 Můžete vytvořit adaptér diagnostických dat, která má vliv na počítači, kde se spouští testy nebo počítač, který je součástí prostředí, ve kterém používáte aplikaci spustit v testu. Například shromažďování souborů na testovacím počítači, kde se testy spouštějí, nebo shromažďování souborů na počítači obsluhující v roli webového serveru pro vaši aplikaci.

 Adaptér diagnostických dat, můžete zajistit popisný název, který se zobrazí při vytváření nastavení testů pomocí nástroje Microsoft Test Manager nebo pomocí sady Visual Studio. Nastavení testů umožňují definovat, jaké role počítače se spustí adaptérů konkrétní diagnostických dat ve vašem prostředí, při spuštění testů. Vaše adaptérů diagnostických dat můžete také konfigurovat při vytvoření nastavení testu. Můžete například vytvořit adaptér diagnostických dat, která shromažďuje vlastní protokoly z webového serveru. Při vytváření testovacích nastavení, můžete vybrat možnost spustit tento adaptér diagnostických dat na počítači nebo počítačů, které fungují této role Webový server a můžete upravit konfiguraci pro nastavení testovací shromažďovat pouze poslední tři protokoly, které byly vytvořeny. Další informace o nastavení testu najdete v tématu [shromažďování diagnostických informací pomocí Test nastavení](../test/collect-diagnostic-information-using-test-settings.md).

 Události jsou vyvolány, když spustíte testy, aby adaptér diagnostických dat můžete v tomto bodě provádět úlohy v testu.

> [!IMPORTANT]
> Tyto události může být aktivována v různých vláknech, zejména v případě, že máte testy spouštění na více počítačích. Proto musíte znát možné problémy vláken a není neúmyslně poškozen interních datových vlastní adaptéru. Zajistěte, aby byl adaptér diagnostických dat bezpečné pro přístup z více vláken.

 Následuje částečný seznam klíčů událostí, které můžete použít při vytváření adaptér diagnostických dat. Úplný seznam událostí adaptéru diagnostických dat najdete v tématu abstraktní <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents> třídy.

|Událost|Popis|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.SessionStart>|Začátek spustit test|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.SessionEnd>|Konec spustit test|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseStart>|Spustit všechny testy v testovacím běhu|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseEnd>|Konec všechny testy v testovacím běhu|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestStepStart>|Spuštění každého kroku testu v testu|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestStepEnd>|Konec každý krok testu v testu|

> [!NOTE]
> Po dokončení manuálního testu žádné další události kolekce dat jsou odesílány adaptér diagnostických dat. Když se znovu spustí testu, bude mít nový identifikátor testovacího případu. Pokud uživatel resetuje testu během testu (kterou vyvolá <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseReset> událostí), nebo změny a testovací krok výsledek, žádná data kolekce událost je odeslána do adaptéru diagnostických dat, ale identifikátor testovacího případu zůstává stejná. Pokud chcete zjistit, zda byl obnoven testovacího případu, musíte ve adaptér diagnostických dat sledovat identifikátor testovacího případu.

 Použijte následující postup k vytvoření adaptéru diagnostických dat, která shromažďuje datový soubor, který je založený na informacích, můžete konfigurovat při vytvoření nastavení testu.

 Adaptér projektu kompletní příklad diagnostických dat, včetně editor vlastní konfigurace, najdete v části [ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md).

##  <a name="CreateAdapter"></a> Vytvoření a instalace adaptéru diagnostických dat

#### <a name="to-create-and-install-a-diagnostic-data-adapter"></a>Vytvoření a instalace adaptéru diagnostických dat

1.  Vytvořte nové knihovny tříd.

    1.  Na **soubor** nabídce zvolte **nový**a pak přejděte na **nový projekt**.

    2.  Z **typy projektů**, vyberte jazyk, který chcete použít.

    3.  Z **Visual Studio – nainstalované šablony**, vyberte **knihovny tříd**.

    4.  Zadejte název pro adaptér diagnostických dat.

    5.  Zvolte **OK**.

2.  Přidat sestavení **Microsoft.VisualStudio.QualityTools.ExecutionCommon**.

    1.  V Průzkumníku řešení klikněte pravým tlačítkem na **odkazy** a zvolte **přidat odkaz na** příkaz.

    2.  Zvolte **.NET** a vyhledejte **Microsoft.VisualStudio.QualityTools.ExecutionCommon.dll**.

    3.  Zvolte **OK**.

3.  Přidat sestavení **Microsoft.VisualStudio.QualityTools.Common**.

    1.  V Průzkumníku řešení klikněte pravým tlačítkem na **odkazy** a vyberte **přidat odkaz na** příkaz.

    2.  Zvolte **/.NET**, vyhledejte **Microsoft.VisualStudio.QualityTools.Common.dll**.

    3.  Zvolte **OK**.

4.  Přidejte následující `using` příkazů do souboru třídy:

    ```csharp
    using Microsoft.VisualStudio.TestTools.Common;
    using Microsoft.VisualStudio.TestTools.Execution;
    using System.Linq;
    using System.Text;
    using System.Xml;
    using System;
    ```

5.  Přidat <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorTypeUriAttribute> do třídy pro adaptér diagnostických dat k identifikaci jako adaptéru diagnostických dat, nahraďte **společnosti**, **produktu**, a **verze** s příslušné informace pro adaptér diagnostických dat:

    ```
    [DataCollectorTypeUri("datacollector://Company/Product/Version")]
    ```

6.  Přidat <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorFriendlyNameAttribute> atribut třídy, nahraďte parametry příslušné informace pro adaptér diagnostických dat:

    ```
    [DataCollectorFriendlyName("Collect Log Files", false)]
    ```

     Tento popisný název se zobrazí v testovacích nastavení aktivit.

    > [!NOTE]
    > Můžete také přidat <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> k určení `Type` editoru vaše vlastní konfigurace pro tento adaptér dat a volitelně zadat soubor nápovědy pro editor.
    >
    > Můžete taky použít <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorEnabledByDefaultAttribute> k určení, zda se má vždy povolit.

7.  Třídě adaptéru diagnostických dat musí dědit z <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector> třídy následujícím způsobem:

    ```csharp
    public class MyDiagnosticDataAdapter : DataCollector
    ```

8.  Přidejte místní proměnné následujícím způsobem:

    ```csharp
    private DataCollectionEvents dataEvents;
    private DataCollectionLogger dataLogger;
    private DataCollectionSink dataSink;
    private XmlElement configurationSettings;
    ```

9. Přidat <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector.Initialize*> metoda a **Dispose** metoda. V `Initialize` metody inicializaci jímku dat, všechny konfigurační data z nastavení testů a registraci obslužné rutiny událostí, které chcete použít takto:

    ```csharp
    public override void Initialize(
        XmlElement configurationElement,
        DataCollectionEvents events,
        DataCollectionSink sink,
        DataCollectionLogger logger,
        DataCollectionEnvironmentContext environmentContext)
    {
           dataEvents = events;  // The test events
           dataLogger = logger;  // The error and warning log
           dataSink = sink;      // Saves collected data
           // Configuration from the test settings
           configurationSettings = configurationElement;

           // Register common events for the data collector
           // Not all of the events are used in this class
        dataEvents.SessionStart +=
            new EventHandler<SessionStartEventArgs>(OnSessionStart);
        dataEvents.SessionEnd +=
            new EventHandler<SessionEndEventArgs>(OnSessionEnd);
        dataEvents.TestCaseStart +=
            new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
        dataEvents.TestCaseEnd +=
            new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
    }

    public override void Dispose(bool disposing)
    {
        if (disposing)
        {
            // Unregister the registered events
            dataEvents.SessionStart -=
                new EventHandler<SessionStartEventArgs>(OnSessionStart);
            dataEvents.SessionEnd -=
                new EventHandler<SessionEndEventArgs>(OnSessionEnd);
            dataEvents.TestCaseStart -=
                new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
            dataEvents.TestCaseEnd -=
                new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
        }
    }
    ```

10. Použijte následující kód obslužné rutiny událostí a soukromá metoda ke shromažďování soubor protokolu vygenerovaných během testu:

    ```csharp
    public void OnTestCaseEnd(sender, TestCaseEndEventArgs e)
    {
        // Get any files to be collected that are
        // configured in your test settings
        List<string> files = getFilesToCollect();

        // For each of the files, send the file to the data sink
        // which will attach it to the test results or to a bug
        foreach (string file in files)
        {
            dataSink.SendFileAsync(e.Context, file, false);
        }
    }

    // A private method that returns the file names
    private List<string> getFilesToCollect()
    {
        // Get a namespace manager with our namespace
        XmlNamespaceManager nsmgr =
            new XmlNamespaceManager(
                configurationSettings.OwnerDocument.NameTable);
        nsmgr.AddNamespace("ns",
            "http://MyCompany/schemas/MyDataCollector/1.0");

        // Find all of the "File" elements under our configuration
        XmlNodeList files =
            configurationSettings.SelectNodes(
                "//ns:MyDataCollector/ns:File");

        // Build the list of files to collect from the
        // "FullPath" attributes of the "File" nodes.
        List<string> result = new List<string>();
        foreach (XmlNode fileNode in files)
        {
            XmlAttribute pathAttribute =
                fileNode.Attributes["FullPath"];
            if (pathAttribute != null &&
                !String.IsNullOrEmpty(pathAttribute.Value))
            {
                result.Add(pathAttribute.Value);
            }
        }

        return result;
    }
    ```

     Tyto soubory jsou připojené k výsledky testů. Pokud vytvoříte chyby z nich testování výsledků nebo při použití [!INCLUDE[mtrlong](../test/includes/mtrlong_md.md)], soubory jsou také připojené k chybě.

     Pokud chcete použít vlastní editor ke shromažďování dat použít v nastavení testu, najdete v článku [postupy: vytvoření vlastního editoru dat pro vaše adaptéru diagnostických dat](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md).

11. Chcete-li shromažďovat soubor protokolu, po dokončení testu v závislosti na to, co uživatel nakonfigurované v nastavení testu, musíte vytvořit `App.config` souboru a přidejte ji do vašeho řešení. Tento soubor má následující formát a musí obsahovat identifikátor URI pro adaptér diagnostických dat pro identifikaci. Nahradit skutečné hodnoty "Společnosti nebo ProductName nebo verze".

    > [!NOTE]
    > Pokud není nutné konfigurovat žádné informace pro adaptér diagnostických dat, není potřeba, vytvořte konfigurační soubor.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <configuration>
      <configSections>
        <section name="DataCollectorConfiguration" type="Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationSection, Microsoft.VisualStudio.QualityTools.ExecutionCommon, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a "/>
      </configSections>
      <DataCollectorConfiguration xmlns="http://microsoft.com/schemas/VisualStudio/TeamTest/2010">
        <DataCollector typeUri="datacollector://MyCompany/MyProduct/1.0">
          <DefaultConfiguration>
            <!-- Your default config settings -->
            <Binaries>
              <Binary FullPath="C:\Example\Example.dll"/>
              <Binary FullPath="\\Server2\Example2.dll"/>
            </Binaries>
            <Symbols>
              <Symbol FullPath="\\ExampleServer\ExampleSymbol.pdb"/>
            </Symbols>
          </DefaultConfiguration>
        </DataCollector>
      </DataCollectorConfiguration>
    </configuration>
    ```

    > [!NOTE]
    > Výchozí konfigurace element může obsahovat žádná data, která požadujete. Pokud uživatel nekonfiguruje adaptér diagnostických dat v nastavení testů a výchozí data se předá adaptér diagnostických dat, když se spustí. Protože soubor XML, který je přidat do `<DefaultConfigurations>` oddíl není pravděpodobné, že součást deklarované schéma, můžete ignorovat všechny chyby XML vygeneruje.
    >
    > Existují další příklady konfigurační soubory v následující cestě založené na instalační adresář: **10.0\Common7\IDE\PrivateAssemblies\DataCollectors Program Files\Microsoft Visual Studio**.

     Další informace o tom, jak nakonfigurovat nastavení testu pro používání prostředí při spuštění testů najdete v tématu [shromažďování diagnostických dat v manuálních testech (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

     Další informace o instalaci konfiguračního souboru, najdete v části [postupy: instalace vlastního adaptéru diagnostických dat](../test/how-to-install-a-custom-diagnostic-data-adapter.md)

12. Vytvoření vlastního řešení k vytvoření vašeho sestavení adaptéru diagnostických dat.

13. Informace o instalaci vlastního editoru najdete v tématu [postupy: instalace vlastního adaptéru diagnostických dat](../test/how-to-install-a-custom-diagnostic-data-adapter.md).

14. Další informace o tom, jak nakonfigurovat nastavení testu pro používání prostředí při spuštění testů najdete v tématu [shromažďování diagnostických dat v manuálních testech (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

15. Pokud chcete vybrat adaptér diagnostických dat, musí nejprve vyberte existujícího nastavení testu nebo vytvořte novou z Microsoft Test Manager nebo Visual Studio. Adaptér se zobrazí na **datové a diagnostické** kartě nastavení testu s popisným názvem, který jste přiřadili k třídě.

16. Nastavte tyto otestovat nastavení jako aktivní. Další informace o nastavení testu najdete v tématu [shromažďování diagnostických informací pomocí Test nastavení](../test/collect-diagnostic-information-using-test-settings.md).

17. Spouštění testů pomocí nastavení testů adaptér diagnostických dat vybraná.

   Datový soubor, který jste zadali, je připojený k si výsledky testu.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorTypeUriAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorFriendlyNameAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorEnabledByDefaultAttribute>
- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)
- [Shromažďování diagnostických dat v manuálních testech (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)
- [Shromažďování diagnostických dat při testování (VSTS)](/vsts/manual-test/collect-diagnostic-data)
- [Postupy: vytvoření vlastního editoru dat pro adaptér diagnostických dat](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
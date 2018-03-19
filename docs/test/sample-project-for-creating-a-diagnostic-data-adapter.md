---
title: "Ukázkový projekt pro vytvoření adaptéru diagnostických dat v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Diagnostic Data Adapter [Visual Studio ALM]
- samples. Diagnostic Data Adapter [Visual Studio ALM]
- Diagnostic Data Adapter, sample
ms.assetid: 548bdc5e-338f-4be7-a555-e6a2efb1df6b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 0b37512405442b327bb4b9688a39bfc4c99ea594
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="sample-project-for-creating-a-diagnostic-data-adapter"></a>Ukázkový projekt pro vytvoření adaptéru diagnostických dat

"MyDiagnosticDataAdapter" je adaptér jednoduché diagnostických dat, který můžete připojit soubor protokolu pro výsledky testů, při spuštění testů.

 Budete potřebovat oprávnění správce na libovolném počítači kde kolekce diagnostických dat nebo konfigurace je nainstalován editor.

## <a name="example-data-adapter"></a>Příklad adaptér dat

Tento příklad ukazuje, jak provádět následující úlohy:

-   Použití atributů zjistitelnost třídu do nástroje Microsoft Test Manager jako adaptéru diagnostických dat.

-   Použití atributů zjistitelnost třídu uživatelského ovládacího prvku do nástroje Microsoft Test Manager jako editor používat ke změně konfigurace pro adaptér diagnostických dat.

-   Přístup k výchozí konfigurační data.

-   Registrace pro konkrétní shromažďování diagnostických dat události.

-   Připojte odesláním do souboru protokolu <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink>.

```csharp
// My Data Collector Class
using Microsoft.VisualStudio.TestTools.Common;
using Microsoft.VisualStudio.TestTools.Execution;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Xml;
using System;

namespace MyCompany.MyDiagnosticDataAdapters
{
    // Provide a URI and friendly name for your diagnostic data adapter
    [DataCollectorTypeUri("datacollector://MyCompany/MyDataCollector/1.0")]
    [DataCollectorFriendlyName("Collect Log Files sample", false)]
    // Designate your chosen configuration editor
    [DataCollectorConfigurationEditor(
        "configurationeditor://MyCompany/MyDataConfigEditor/1.0")]
    public class MyDataCollector : DataCollector
    {
        private DataCollectionEvents dataEvents;
        private DataCollectionLogger dataLogger;
        private DataCollectionSink dataSink;
        private XmlElement configurationSettings;

        // Required method called by the testing framework
        public override void Initialize(
            XmlElement configurationElement,
            DataCollectionEvents events,
            DataCollectionSink sink,
            DataCollectionLogger logger,
            DataCollectionEnvironmentContext environmentContext)
        {
            dataEvents = events; // The test events
            dataLogger = logger; // The error and warning log
            dataSink = sink;     // Saves collected data
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
            dataEvents.DataRequest +=
                new EventHandler<DataRequestEventArgs>(OnDataRequest);
        }

        protected override void Dispose(bool disposing)
        {
            if (disposing)
            {
                dataEvents.SessionStart -=
                    new EventHandler<SessionStartEventArgs>(OnSessionStart);
                dataEvents.SessionEnd -=
                    new EventHandler<SessionEndEventArgs>(OnSessionEnd);
                dataEvents.TestCaseStart -=
                    new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
                dataEvents.TestCaseEnd -=
                    new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
                dataEvents.DataRequest -=
                    new EventHandler<DataRequestEventArgs>(OnDataRequest);
            }
        }

        #region Event Handlers
        public void OnSessionStart(object sender, SessionStartEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnSessionEnd(object sender, SessionEndEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnTestCaseStart(object sender, TestCaseEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnTestCaseEnd(object sender, TestCaseEndEventArgs e)
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

        public void OnDataRequest(object sender, DataRequestEventArgs e)
        {
            // TODO: Provide implementation
            // Most likely this occurs because a bug is being filed
        }
        #endregion

        // A private method to collect the configured file names
        private List<string> getFilesToCollect()
        {
            // Seetup namespace manager with our namespace
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
    }
}
```

## <a name="example-configuration-editor"></a>Příklad konfigurace editoru

Toto je Ukázková konfigurace editor pro adaptér diagnostických dat. Přidat uživatelský ovládací prvek do projektu a vytvořit velmi jednoduchý formulář, který má popisek ("název souboru protokolu:") a textové pole s názvem "FileTextBox".

```csharp
using Microsoft.VisualStudio.TestTools.Common;
using Microsoft.VisualStudio.TestTools.Execution;
using System.Collections.Generic;
using System.ComponentModel;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
using System.Xml;
using System;

namespace MyCompany.DiagnosticDataAdapters.ConfigurationEditors
{
    [DataCollectorConfigurationEditorTypeUri(
        "configurationeditor://MyCompany/MyConfigEditor/1.0")]
    public partial class MyDataConfigEditor :
        UserControl, IDataCollectorConfigurationEditor
    {
        private DataCollectorSettings collectorSettings;

        // Create a private property for the service provider
        private IServiceProvider ServiceProvider { get; set; }

        // Constructor
        public MyConfigurationEditor()
        {
            InitializeComponent();
        }

        // Required method called by the testing framework
        public void Initialize(
            IServiceProvider svcProvider,
            DataCollectorSettings settings)
        {
            ServiceProvider = svcProvider;
            collectorSettings = settings;

            // Display the file name as listed in the settings file.
            // If the configuration has not been updated before, this
            // data will be provided by the default configuration
            // section from <nameofcollector>.dll.config:
            // <DefaultConfiguration>
            //   <MyCollectorName
            //       xmlns="http://MyCompany/schemas/ProductName/Version");
            //     <File FullPath="C:\temp\logfile1.txt" />
            //   </MyCollectorName>
            // </DefaultConfiguration>
            this.SuspendLayout();
            this.FileTextBox.Text = GetText(collectorSettings.Configuration);
            this.ResumeLayout();
        }

        // Can be used to verify data before saving it
        public bool VerifyData()
        {
            // Not currently verifying data
            return true;
        }

        // Reset to default value from XML configuration
        // using a custom method
        public void ResetToAgentDefaults()
        {
            this.FileTextBox.Text =
                getText(collectorSettings.DefaultConfiguration);
        }

        // Saves data changed in the editor to the test configuration
        // settings. Does not change the default value.
        public DataCollectorSettings SaveData()
        {
            collectorSettings.Configuration.InnerXml =
                String.Format(
                    @"<MyCollectorName
      xmlns=""http://MyCompany/schemas/MyDataCollector/1.0"">
  <File FullPath=""{0}"" />
</MyCollectorName>",
                    FileTextBox.Text);
            return collectorSettings;
        }

        // Reads the configuration settings
        private string getText(XmlElement element)
        {
            // Setup namespace manager with our namespace
            XmlNamespaceManager nsmgr =
                new XmlNamespaceManager(
                    element.OwnerDocument.NameTable);

            // Find all the "File" elements under our configuration
            XmlNodeList files = element.SelectNodes("//ns:MyDataCollector/ns:File", nsmgr);

            string result = String.Empty;
            if (files.Count > 0)
            {
                XmlAttribute pathAttribute = files[0].Attributes["FullPath"];
                if (pathAttribute != null &&
                    !String.IsNullOrEmpty(pathAttribute.Value))
                {
                    result = pathAttribute.Value;
                }
            }

            return result;
        }
    }
}
```

## <a name="example-configuration-file"></a>Příklad konfiguračního souboru

Toto je vzorový konfigurační soubor pro vaše editor konfigurací kolekce diagnostická data.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <section
      name="DataCollectorConfiguration"
      type="Microsoft.VisualStudio.QualityTools.Execution.DataCollectorConfigurationSection,
        Microsoft.visualStudio.QualityTools.ExecutionCommon,
        Version=4.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f7f11d50a3a" />
  </configSections>
  <DataCollectorConfiguration
      xmlns="http://microsoft.com/schemas/VisualStudio/TeamTest/11">
    <DataCollector
        typeUri="datacollector://MyCompany/MyDataCollector/1.0">
      <DefaultConfiguration>
        <!-- Your default config settings-->
        <File FullPath="c:\temp\logfile1.txt" />
      </DefaultConfiguration>
    </DataCollector>
  </DataCollectorConfiguration>
</configuration>

```

## <a name="compiling-the-code"></a>Probíhá kompilace kódu

### <a name="to-create-the-code-project-for-this-diagnostic-adapter"></a>Vytvoření projektu kódu pro tento adaptér diagnostiky

1.  Vytvoření nového projektu knihovny tříd s názvem "MyDataCollector".

2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a zvolte **vlastnosti**. Vyberte složku, chcete-li přidat, zvolte **cesty odkazů** a klikněte na tlačítko se třemi tečkami (**...** ).

     **Vyberte odkaz na cestu** se zobrazí dialogové okno.

3.  Vyberte následující cestu, založené na instalační adresář: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies*. Zvolte **OK**.

4.  Chcete-li přidat složku do cesty k odkazu, zvolte **přidat složku**.

     Složka se zobrazí v seznamu cest odkaz.

5.  Vyberte **Uložit vše** ikonu a uložte odkaz na cesty.

6.  Přidat sestavení **Microsoft.VisualStudio.QualityTools.ExecutionCommon**.

    1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **odkazy** a potom zvolte **přidat odkaz na**.

    2.  Zvolte **Procházet** a vyhledejte **Microsoft.VisualStudio.QualityTools.ExecutionCommon.dll**.

         Toto sestavení budou nacházet v *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies*.

    3.  Zvolte **OK**.

7.  Přidat sestavení **Microsoft.VisualStudio.QualityTools.Common**.

    1.  V Průzkumníku řešení klikněte pravým tlačítkem na **odkazy** a vyberte **přidat odkaz na**.

    2.  Zvolte **Procházet** a vyhledejte **Microsoft.VisualStudio.QualityTools.Common.dll**.

         Toto sestavení budou nacházet v *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies*.

    3.  Zvolte **OK**.

8.  Zkopírujte Třída adaptéru diagnostických dat, který byl uveden výše v tomto dokumentu do třídy pro knihovny tříd. Uložte tuto třídu.

9. Chcete-li přidat uživatelský ovládací prvek do projektu, klikněte pravým tlačítkem na projekt MyDataCollector v Průzkumníku řešení bod **přidat**a potom zvolte **uživatelský ovládací prvek**. Zvolte **přidat**.

10. Pomocí sady nástrojů přidat uživatelský ovládací prvek popisek a změnit vlastnosti textu k **název souboru:**.

11. Pomocí panelu Přidat textové pole do uživatelského ovládacího prvku a změňte název **textBoxFileName**.

12. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uživatelský ovládací prvek a potom zvolte **zobrazení kódu.** Tato třída řízení uživatele nahraďte třída ovládacích prvků uživatele, který byl uveden výše v tomto dokumentu. Uložte tuto třídu.

    > [!NOTE]
    > Ve výchozím nastavení se nazývá uživatelského ovládacího prvku UserControl1. Ujistěte se, že kód uživatelského ovládacího prvku třídu používá název svého uživatelského ovládacího prvku.

13. Vytvoření konfiguračního souboru v **Průzkumníku řešení** pravým tlačítkem na řešení, přejděte na **přidat**a potom zvolte **novou položku**. Vyberte, chcete-li vybrat **konfigurační soubor aplikace**a potom zvolte **přidat**. Bude přidáno souboru, který je pojmenován **App.config** do řešení.

14. Zkopírujte soubor XML ve vzorku, který byl dříve zadán do souboru XML. Uložte soubor.

15. Sestavte řešení a poté zkopírujte vytvořený sestavení a `App.config` soubor do *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors* adresáře.

16. Vytvoření nastavení testu, které používají tento adaptér diagnostických dat vlastní. Nakonfigurujte nastavení testu shromažďování soubor, který již existuje.

     Pokud spouštíte testy Microsoft Test Manager, můžete přiřadit těchto nastavení testů do testovacího plánu před spuštěním testů nebo používají spustit pomocí možnosti příkazu k přiřazení nastavení testů a přepsat nastavení testů. Další informace o nastavení testu najdete v tématu [shromažďování diagnostických informací pomocí Test nastavení](../test/collect-diagnostic-information-using-test-settings.md).

17. Spouštění testů pomocí nastavení testů adaptér diagnostických dat vybraná.

     Datový soubor, který jste zadali bude připojen k si výsledky testu, pokud se test spustí.

## <a name="see-also"></a>Viz také

- [Postupy: vytvoření adaptéru diagnostických dat](../test/how-to-create-a-diagnostic-data-adapter.md)
- [Postupy: vytvoření vlastního editoru dat pro adaptér diagnostických dat](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [Postupy: instalace vlastního adaptéru diagnostických dat](../test/how-to-install-a-custom-diagnostic-data-adapter.md)
- [Vytvoření adaptéru diagnostických dat pro shromáždění vlastních dat nebo ovlivnění testovacího počítače](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
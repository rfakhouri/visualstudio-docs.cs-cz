---
title: "Vytvoření vlastního editoru dat adaptéru diagnostických dat v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Diagnostic Data Adapter, creating custom editor
ms.assetid: 24970227-d1ea-4f6d-9839-e911478848ba
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: d1426d6e51ac132ee766913e69827df1d9558fba
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter"></a>Postupy: Vytvoření vlastního editoru dat pro adaptér diagnostických dat

Když vytvoříte adaptéru diagnostických dat, můžete chtít pro koncového uživatele lze nakonfigurovat konkrétní data, pokud je vybrána vašeho vlastního adaptéru diagnostických dat pro jejich nastavení testu. Můžete například vybrat konfigurační data, která určuje, které klíče registru k extrakci, jakou úroveň zatížení sítě k simulaci, nebo v adresář, kterému k vyhledání dočasné soubory nebo pracovní soubory připojit.

Nastavit počáteční hodnoty pro adaptér diagnostických dat, musíte použít konfigurační soubor. Můžete zadat vlastní editor povolit uživatelům upravit konfigurační data.

Pokud chcete vytvořit vlastní editor, vytvoříte uživatelský ovládací prvek, který implementuje <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>.

Můžete použít adaptér diagnostických dat <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> určete editor třídu sloužící k úpravám nastavení konfigurace diagnostická data.

Je také zadat výchozí konfigurační data, která chcete použít.  V tématu [ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md) pro ukázkové výchozí konfiguraci.

Použijte následující postup k vytvoření vlastního editoru aktualizace dat pro nastavení testovací při použití adaptéru diagnostických vaše vlastní data.

> [!NOTE]
> K vytvoření vlastního editoru, musíte nejdřív vytvořit adaptér diagnostických dat, který má <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> použít pro třídu. Můžete použít nepovinný <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute.HelpUri*> vlastnost tento atribut zadat zdroj obsahu nápovědy pro vaše editor. Další informace o tom, jak vytvořit adaptér diagnostických dat najdete v tématu [postupy: vytvoření adaptéru diagnostických dat](../test/how-to-create-a-diagnostic-data-adapter.md).

Adaptér projektu kompletní příklad diagnostických dat, včetně editor vlastní konfigurace, najdete v části [ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md).

## <a name="to-create-a-custom-editor-for-your-diagnostic-data-adapter"></a>Chcete-li vytvořit vlastní editor pro adaptér diagnostických dat

1.  Vytvoření uživatelského ovládacího prvku v projektu pro adaptér diagnostických dat:

    1.  Klikněte pravým tlačítkem na projekt kód, který obsahuje třídě adaptéru diagnostických dat, přejděte na **přidat** a pak přejděte na **uživatelský ovládací prvek**.

    2.  V tomto příkladu přidání štítku do formuláře se tento text: **název datového souboru:** a textové pole s názvem **FileTextBox** umožní, aby uživatel zadal potřebná data.

    > [!NOTE]
    > Aktuálně jsou podporovány pouze ovládací prvky Windows Forms uživatele.

2.  Přidejte tyto řádky v části prohlášení:

    ```csharp
    using System.Xml;
    using Microsoft.VisualStudio.TestTools.Common;
    using Microsoft.VisualStudio.TestTools.Execution;
    ```

3.  Ujistěte se, toto uživatelského ovládacího prvku do vlastní editor.

    1.  Klikněte pravým tlačítkem na uživatelský ovládací prvek v projektu kódu a přejděte na **zobrazit kód**.

    2.  Set – třída pro implementaci rozhraní editoru <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor> následujícím způsobem:

    ```csharp
    public partial class MyDataConfigEditor :
         UserControl, IDataCollectorConfigurationEditor
    ```

    1.  Klikněte pravým tlačítkem na <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor> v kódu a vyberte **implementovat rozhraní** příkaz. Metody, které je nutné implementovat pro toto rozhraní se přidají do vaší třídy.

    2.  Přidat <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> pro váš uživatelský ovládací prvek pro vaše editor k identifikaci jako editor pro adaptér diagnostických dat, nahraďte **společnosti**, **produktu**, a **verze** s příslušné informace pro adaptér diagnostických dat:

        ```csharp
        [DataCollectorConfigurationEditorTypeUri(
            "configurationeditor://MyCompany/MyConfigEditor/1.0")]
        ```

4.  Přidejte dva privátní proměnné následujícím způsobem:

    ```csharp
    private DataCollectorSettings collectorSettings;
    private IServiceProvider ServiceProvider { get; set; }
    ```

5.  Přidáte kód pro inicializaci vaší editor pro adaptér diagnostických dat. Výchozí hodnoty můžete přidat na pole v svého uživatelského ovládacího prvku pomocí dat, který je v nastavení proměnné. Toto je data, která je v `<DefaultConfiguration>` element v konfigurační soubor XML pro adaptér.

    ```csharp
    public void Initialize(
        IServiceProvider svcProvider,
        DataCollectorSettings settings)
    {
        ServiceProvider = svcProvider;
        collectorSettings = settings;

        // Display the default file name as listed in the settings file.
        this.SuspendLayout();
        this.FileTextBox.Text = getText(collectorSettings.Configuration);
        this.ResumeLayout();
    }
    ```

6.  Přidejte kód k uložení dat z vaše ovládací prvky ve svém editoru zpět do formátu XML, který vyžaduje adaptér diagnostických dat rozhraní API následujícím způsobem:

    ```csharp
    public DataCollectorSettings SaveData()
    {
        collectorSettings.Configuration.InnerXml =
            String.Format(
    @"<MyCollectorName
        xmlns=""http://MyCompany/schemas/MyDiagnosticDataCollector/1.0"">
      <File FullPath=""{0}"" />
    </MyCollectorName>",
        FileTextBox.Text);
        return collectorSettings;
    }
    ```

7.  Pokud je pro vás důležité, přidejte kód, chcete-li ověřit správnost dat v `VerifyData` metoda, nebo může mít metoda vrátí `true`.

    ```csharp
    public bool VerifyData()
    {
        // Not currently verifying data
        return true;
    }
    ```

8.  (Volitelné) Můžete přidat kód pro obnovení dat počáteční nastavení, které jsou k dispozici v konfiguračním souboru XML v `ResetToAgentDefaults()` metoda, která používá privátní `getText()` metoda.

    ```csharp
    // Reset to default value from XML configuration
    // using a custom getText() method
    public void ResetToAgentDefaults()
    {
        this.FileTextBox.Text = getText(collectorSettings.DefaultConfiguration);
    }

    // Local method to read the configuration settings
    private string getText(XmlElement element)
    {
        // Setup namespace manager with our namespace
        XmlNamespaceManager nsmgr =
            new XmlNamespaceManager(
                element.OwnerDocument.NameTable);

        // Find all the "File" elements under our configuration
        XmlNodeList files = element.SelectNodes("//ns:MyCollectorName/ns:File", nsmgr);

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
    ```

9. Sestavte řešení. Zkopírujte sestavení adaptéru diagnostických dat a konfigurační soubor XML (`<diagnostic data adapter name>.dll.config`) do následujícího umístění založené na instalační adresář: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\ PrivateAssemblies\DataCollectors*.

    > [!NOTE]
    > I když editor konfigurací může být v projektu a sestavení, které se liší od adaptér diagnostických dat, může také být ve stejném sestavení.

10. Pokud chcete použít při testování Adaptér diagnostických dat, musíte vybrat ze seznamu existujícího nastavení testu nebo vytvořte novou z Microsoft Test Manager nebo Visual Studio a vyberte adaptér diagnostických dat.

     Adaptér se zobrazí na **datové a diagnostické** kartě nastavení testu s popisným názvem, který jste přiřadili k třídě.

11. Chcete-li nakonfigurovat adaptér diagnostických dat pro testovací nastavení, zvolte **konfigurace** vedle názvu adaptéru.

     Vlastní editor se nyní zobrazí.

12. Upravte pole ve vaší vlastní editor podle potřeby a potom vyberte **Uložit**.

13. Pokud spouštíte testy Microsoft Test Manager, můžete přiřadit těchto nastavení do testovacího plánu testů, než můžete spustit testy nebo použít **spustit s možností** příkaz přiřadit nastavení testů a přepsat nastavení testů. Další informace o nastavení testu najdete v tématu [shromažďování diagnostických informací pomocí Test nastavení](../test/collect-diagnostic-information-using-test-settings.md).

14. Než použijete vaše nové editor konfigurací pomocí adaptéru diagnostických dat, musíte použít <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> pro různé třídy adaptéru diagnostických dat, který chcete použít editor a znovu zkompiluje, přeinstalujte je na klientském počítači. Další informace o tom, jak nainstalovat adaptérů diagnostických dat a konfigurace editory najdete v tématu [postupy: instalace vlastního adaptéru diagnostických dat](../test/how-to-install-a-custom-diagnostic-data-adapter.md).

15. Spouštění testů pomocí nastavení testů adaptér diagnostických dat vybraná.

     Datový soubor, který jste zadali ve svém editoru je připojený k si výsledky testu.

 Další informace o tom, jak nakonfigurovat nastavení testu pro používání prostředí při spuštění testů najdete v tématu [shromažďování diagnostických dat při testování (VSTS)](/vsts/manual-test/collect-diagnostic-data) nebo [shromažďování diagnostických dat v manuálních testech (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- [Vytvoření adaptéru diagnostických dat pro shromáždění vlastních dat nebo ovlivnění testovacího počítače](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)
- [Ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
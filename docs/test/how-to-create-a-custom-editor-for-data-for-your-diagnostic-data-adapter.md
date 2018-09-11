---
title: Vytvoření vlastního editoru dat pro adaptér diagnostických dat v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, creating custom editor
ms.assetid: 24970227-d1ea-4f6d-9839-e911478848ba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 372cc01f1d7a0a21832ff099472e444d43d7a699
ms.sourcegitcommit: 28909340cd0a0d7cb5e1fd29cbd37e726d832631
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44320537"
---
# <a name="how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter"></a>Postupy: vytvoření vlastního editoru dat pro adaptér diagnostických dat

Při vytváření adaptéru diagnostických dat, můžete chtít povolit konfiguraci určitých dat při výběru vašeho vlastního adaptéru diagnostických dat pro nastavení jejich testu koncovému uživateli. Například můžete vybrat konfigurační data, která určuje, které klíče registru chcete extrahovat, jakou úroveň zatížení sítě chcete simulovat nebo ve kterém adresáři chcete hledat dočasné soubory nebo pracovní soubory pro připojení.

K nastavení počátečních hodnot pro adaptér diagnostických dat, musíte použít konfigurační soubor. Můžete zadat vlastní editor umožňující uživateli upravit konfigurační data.

Pokud chcete vytvořit vlastní editor, vytvoříte uživatelský ovládací prvek, který implementuje <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>.

Můžete použít adaptér diagnostických dat <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> k určení třídy editor pro úpravu nastavení konfigurace diagnostická data.

Můžete také určit výchozí konfigurační data, která chcete použít.  Zobrazit [ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md) Vzorová výchozí konfigurace.

Chcete-li vytvořit vlastní editor k aktualizaci dat pro nastavení testu při použití vašeho vlastního adaptéru diagnostických dat. pomocí následujícího postupu.

> [!NOTE]
> Pokud chcete vytvořit vlastní editor, je nutné nejprve vytvořit adaptér diagnostických dat, který má <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> použít pro třídu. Můžete použít nepovinnou <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute.HelpUri*> vlastnosti v tomto atributu k určení zdroje obsahu nápovědy pro editor. Další informace o tom, jak vytvořit adaptér diagnostických dat naleznete v tématu [postupy: vytvoření adaptéru diagnostických dat](../test/how-to-create-a-diagnostic-data-adapter.md).

Kompletní příklad diagnostických dat adaptéru projektu, včetně vlastního konfiguračního editoru, najdete v části [ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md).

## <a name="to-create-a-custom-editor-for-your-diagnostic-data-adapter"></a>K vytvoření vlastního editoru pro adaptér diagnostických dat

1.  Vytvoření uživatelského ovládacího prvku v projektu pro adaptér diagnostických dat:

    1.  Klikněte pravým tlačítkem na projekt kódu, který obsahuje vaše třída adaptéru diagnostických dat, přejděte na **přidat** a přejděte na **uživatelský ovládací prvek**.

    2.  V tomto příkladu přidejte popisek do formuláře s tímto textem: **název datového souboru:** a textové pole s názvem **FileTextBox** , který vám umožní uživateli zadat potřebné údaje.

    > [!NOTE]
    > Aktuálně jsou podporovány pouze ovládací prvky Windows Forms uživatele.

2.  Přidejte tyto řádky do části deklarace:

    ```csharp
    using System.Xml;
    using Microsoft.VisualStudio.TestTools.Common;
    using Microsoft.VisualStudio.TestTools.Execution;
    ```

3.  Převeďte tento uživatelský ovládací prvek na vlastní editor.

    1.  Klikněte pravým tlačítkem na uživatelský ovládací prvek v projektu kódu a přejděte na **zobrazení kódu**.

    2.  Nastavení třídu pro implementaci rozhraní editoru <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor> následujícím způsobem:

    ```csharp
    public partial class MyDataConfigEditor :
         UserControl, IDataCollectorConfigurationEditor
    ```

    1.  Klikněte pravým tlačítkem na <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor> v kódu a vyberte **implementovat rozhraní** příkazu. Metody, které je nutné implementovat pro toto rozhraní se přidají do vaší třídy.

    2.  Přidat <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> do uživatelského ovládacího prvku pro editor k jeho identifikaci jako editoru adaptéru diagnostických dat, nahrazení **společnosti**, **produktu**, a **verze** s odpovídajícími informacemi pro adaptér diagnostických dat:

        ```csharp
        [DataCollectorConfigurationEditorTypeUri(
            "configurationeditor://MyCompany/MyConfigEditor/1.0")]
        ```

4.  Přidejte dvě soukromé proměnné následujícím způsobem:

    ```csharp
    private DataCollectorSettings collectorSettings;
    private IServiceProvider ServiceProvider { get; set; }
    ```

5.  Přidejte kód pro inicializaci editoru pro adaptér diagnostických dat. Výchozí hodnoty do polí můžete přidat do vašeho uživatelského ovládacího prvku pomocí dat, která je v nastavení proměnné. Jedná se o data, která je v `<DefaultConfiguration>` element v konfiguračním souboru XML pro adaptér.

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

6.  Přidejte kód pro uložení dat z ovládacích prvků v editoru zpět do formátu XML požadovaného rozhraním API adaptéru diagnostických dat následujícím způsobem:

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

7.  Pokud je pro vás důležité, přidejte kód pro ověření správnosti v data `VerifyData` metodu, nebo může mít metoda vrátit `true`.

    ```csharp
    public bool VerifyData()
    {
        // Not currently verifying data
        return true;
    }
    ```

8.  (Volitelné) Můžete přidat kód pro obnovení dat do původního nastavení, které jsou k dispozici v konfiguračním souboru XML v `ResetToAgentDefaults()` metodu, která používá soukromou `getText()` metody.

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

9. Sestavte řešení. Zkopírujte sestavení adaptéru diagnostických dat a konfigurační soubor XML (`<diagnostic data adapter name>.dll.config`) do následujícího umístění založeného na instalačním adresáři: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\ PrivateAssemblies\DataCollectors*.

    > [!NOTE]
    > Přestože editor konfigurace může být v projektu a sestavení, které se liší od adaptéru diagnostických dat, může také být ve stejném sestavení.

10. Pokud chcete použít při testování Adaptér diagnostických dat, musíte vybrat ze seznamu existující nastavení testu nebo vytvořit nový štítek z Microsoft Test Manager nebo Visual Studio a vybrat adaptér diagnostických dat.

     Adaptér se zobrazí na **dat a diagnostiky** karty ve vašem nastavení testu s popisným názvem, který jste přiřadili do třídy.

11. Chcete-li nakonfigurovat adaptér diagnostických dat pro nastavení testu, zvolte **konfigurovat** vedle názvu adaptéru.

     Vlastní editor je nyní zobrazen.

12. Upravte pole ve vlastním editoru podle potřeby a klikněte na tlačítko **Uložit**.

13. Pokud spouštíte testy z nástroje Microsoft Test Manager, můžete přiřadit tato nastavení testu do plánu testování před spuštěním testů nebo pomocí **spustit s možnostmi** příkaz pro přidělení nastavení testu a přepsání nastavení testu. Další informace o nastaveních testu naleznete v tématu [shromažďování diagnostických informací pomocí nastavení testu](../test/collect-diagnostic-information-using-test-settings.md).

14. Než budete moct použít vaši novou konfiguraci editoru s adaptérem diagnostických dat, musíte použít <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> pro každou třídu adaptéru diagnostických dat, který chcete použít editor a znovu zkompilovat a znovu nainstalovat klientský počítač. Další informace o tom, jak nainstalovat adaptéry diagnostických dat a konfigurační editory, naleznete v tématu [postupy: instalace vlastního adaptéru diagnostických dat](../test/how-to-install-a-custom-diagnostic-data-adapter.md).

15. Spusťte testy pomocí nastavení testu společně s výběrem adaptéru diagnostiky dat vybrali.

     K výsledkům testů je připojen datový soubor, který jste zadali v editoru.

 Další informace o tom, jak nakonfigurovat nastavení testu pro použití prostředí při spuštění testů, naleznete v tématu [shromažďování diagnostických dat při testování (testovací plány Azure)](/azure/devops/test/collect-diagnostic-data?view=vsts) nebo [shromažďování diagnostických dat v ruční testy () Plány testování v Azure)](/azure/devops/test/mtm/collect-more-diagnostic-data-in-manual-tests?view=vsts).

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- [Vytvoření adaptéru diagnostických dat pro shromáždění vlastních dat nebo ovlivnění testovacího počítače](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [Shromažďování diagnostických údajů pomocí nastavení testů](../test/collect-diagnostic-information-using-test-settings.md)
- [Ukázkový projekt pro vytvoření adaptéru diagnostických dat](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
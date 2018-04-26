---
title: Vytvoření modulu Plugin pro testy výkonnosti webu rekordéru v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, recorder plug-in
ms.assetid: 6fe13be1-aeb5-4927-9bff-35950e194da9
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 008275d4e0ff094c7933b4e0bae89055acd4bf8e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-recorder-plug-in"></a>Postupy: Vytvoření modulu plugin rekordéru

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin> Umožňuje upravovat zaznamenaná testu výkonnosti webu. Úpravy dojde po volbě **Zastavit** ve výkonu webové otestovat zapisovač nástrojů, ale před testovacího se uložit a zobrazovat v Editor testů výkonnosti webu.

Modul plugin rekordéru umožňuje provádět vlastní vlastní korelace dynamických parametrů. Pomocí funkce integrované korelace testy výkonnosti webu detekovat dynamických parametrů v webového záznamu po dokončení, nebo při použití **Převedení dynamických parametrů na parametry testu webové** na výkon webové Panel nástrojů editoru testů. Ale předdefinovaných při zjišťování funkce vždy nenajde dynamických parametrů. Například nenajde ID relace, které obvykle získá svou hodnotu změnit mezi 5 až 30 minut. Proto je nutné ručně provést proces korelace.

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin> Umožňuje psát kód pro vaše vlastní vlastní modul plug-in. Tento modul plug-in můžete provést srovnávací nebo upravovat testu výkonnosti webu v mnoha směrech před jeho právě uložili a zobrazovat v Editor testů výkonnosti webu. Pokud zjistíte, že konkrétní dynamickou proměnnou, která má ke korelaci pro velké množství vaše záznamy, proto můžete automatizovat proces.

Je několik způsobů, jak lze modul plugin rekordéru pro přidání extrakce a pravidel ověřování, přidání kontextových parametrů, nebo převod komentáře transakce výkonu webových testů.

Následující postupy popisují postup vytvoření modulu Plugin rekordéru elementární kód, modul plug-in nasadit a spouštět modul plug-in. Následující postupy ukázkový kód ukazuje, jak používat Visual C# k vytvoření modulu Plugin rekordéru korelace vlastní dynamický parametr.

## <a name="creating-a-recorder-plug-in"></a>Vytváření modulů Plugin rekordéru

### <a name="to-create-a-recorder-plug-in"></a>K vytvoření modulu Plugin rekordéru

1.  Otevřete řešení obsahující webové výkonu a zatížení testovacího projektu s testu výkonnosti webu, pro kterou chcete vytvoření modulu Plugin rekordéru.

2.  V Průzkumníku řešení klikněte pravým tlačítkem na řešení, vyberte **přidat**a potom zvolte **nový projekt**.

     **Přidat nový projekt** se zobrazí dialogové okno.

3.  V části **nainstalovaných šablonách**, vyberte **Visual C#**.

4.  V seznamu šablon, vyberte **knihovny tříd**.

5.  V **název** textového pole zadejte název pro modul plugin rekordéru.

     Knihovny tříd se přidá do Průzkumníka řešení a nová třída je otevřen v editoru kódu.

6.  V Průzkumníku řešení v nové třídy knihovny složce projektu, klikněte pravým tlačítkem myši **odkazy** složky a vyberte **přidat odkaz na**.

    > [!TIP]
    > Je například novou složku projektu knihovny tříd **RecorderPlugins**.

     **Přidat odkaz na** se zobrazí dialogové okno.

7.  Vyberte **.NET** kartě.

8.  Přejděte dolů a vyberte **Microsoft.VisualStudio.QualityTools.WebTestFramework** a potom zvolte **OK**.

     **Microsoft.VisualStudio.QualityTools.WebTestFramework** je přidaný do **odkazy** složky v Průzkumníku řešení.

9. Zapište kód pro vaše modul plugin rekordéru. Nejprve vytvořte novou veřejnou třídu, která je odvozena z <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin>.

10. Přepsání <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin.PostWebTestRecording*> metoda.

    ```csharp
    public class Class1 : WebTestRecorderPlugin
        {
            public override void PostWebTestRecording(object sender, PostWebTestRecordingEventArgs e)
            {
                base.PostWebTestRecording(sender, e);
            }
        }
    ```

     Argumenty událostí získáte dva objekty pro práci s: zaznamenaná výsledek a zaznamenaná testu výkonnosti webu. To vám umožní k iteraci v rámci výsledek vyhledávání pro určité hodnoty a potom přechod na stejném požadavku v testu výkonnosti webu, aby se změny. Můžete také právě upravit testu výkonnosti webu Kdybyste chtěli přidat kontext parametru nebo Parametrizace části adresy URL.

    > [!NOTE]
    > Pokud změníte testu výkonnosti webu, budete také muset nastavit <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostWebTestRecordingEventArgs.RecordedWebTestModified*> vlastnost na hodnotu true: `e.RecordedWebTestModified = true;`

11. Přidejte další kód podle co chcete zapisovač modulu plug-in k provedení po dojde k webového záznamu. Například můžete přidat kód pro zpracování vlastní korelace, jak je znázorněno v následující ukázka. Můžete také vytvářet rekordéru modulu plug-in pro e převodu komentáře transakce nebo přidání pravidel ověřování k výkonu webových testů.

12. Na **sestavení** nabídce zvolte sestavení \<název projektu knihovny tříd >.

13. Dále je nutné nasadit v pořadí pro registraci pomocí sady Visual Studio modul plugin rekordéru.

### <a name="deploy-the-recorder-plug-in"></a>Nasazení modul plugin rekordéru

Po zkompilujete modul plugin rekordéru, je nutné umístit výsledné DLL v jednom ze dvou umístěních:

-   %ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\WebTestPlugins

-   %USERPROFILE%\My Documents\Visual Studio \< *verze*> \WebTestPlugins

> [!WARNING]
> Po zkopírování modul plugin rekordéru mezi těmito dvěma umístěními, musíte restartovat Visual Studio pro modul plug-in, které se má registrovat zapisovač.

### <a name="to-execute-the-recorder-plug-in"></a>Chcete-li spustit modul plugin rekordéru

1.  Vytvořte nový webový test výkonu.

     **Povolit WebTestRecordPlugins** zobrazí dialogové okno.

2.  Zaškrtněte políčko pro modul plugin rekordéru a klepněte na tlačítko OK.

     Po dokončení testu výkonnosti webu záznam nový modul plugin rekordéru bude proveden.

    > [!WARNING]
    > Při spuštění testu výkonnosti webu nebo zátěžový test, který používá modul plug-in, může dojde k chybě podobný následujícímu:
    >
    > **Žádost se nezdařila.: výjimka v \<modulu plug-in > událostí: Nelze načíst soubor nebo sestavení '\<souboru DLL ""modulu Plug-in název >, verze =\<n.n.n.n >, jazykovou verzi = neutral, PublicKeyToken = null, nebo jeden z jeho závislých. Systém nemůže najít zadaný soubor.**
    >
    > To se stává, pokud provedete změny kódu pro všechny moduly plug-in a vytvořit novou verzi knihovny DLL **(verze = 0.0.0.0)**, ale modul plug-in stále odkazuje na původní verze modulu plug-in. Chcete-li tento problém, postupujte takto:
    >
    > 1.  V výkon webové a zatížení testovacího projektu zobrazí se upozornění v odkazech na. Odeberte a znovu přidat odkaz na knihovnu DLL modulu plug-in.
    > 2.  Odeberte modul plug-in z svůj test nebo do příslušného umístění a poté přidat zpět.

## <a name="example"></a>Příklad

Tato ukázka ukazuje, jak vytvořit vlastní zapisovač testu výkonu webu modulu plug-in k provedení korelace vlastní dynamický parametr.

> [!NOTE]
> Úplný seznam všech ukázkový kód je umístěn v dolní části tohoto tématu.

 **Kontrola ukázkový kód**

## <a name="iterate-through-the-result-to-find-first-page-with-reportsession"></a>Výsledek, který má najít první stránka s ReportSession iterace

Tato část ukázka kódu iteruje každý záznam objekt a hledá ReportSession text odpovědi.

```csharp
foreach (WebTestResultUnit unit in e.RecordedWebTestResult.Children)
 {
     WebTestResultPage page = unit as WebTestResultPage;
     if (page != null)
     {
         if (!foundId)
         {
             int indexOfReportSession = page.RequestResult.Response.BodyString.IndexOf("ReportSession");
             if (indexOfReportSession > -1)
             {
```

## <a name="add-an-extraction-rule"></a>Přidání pravidla pro extrakci

Teď, když byl nalezen odpověď, je nutné přidat pravidla pro extrakci. Tato část ukázka kódu vytvoří pomocí pravidla extrakce <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRuleReference> třídy a vyhledá v testu výkonnosti webu přidat pravidla pro extrakci do správnou žádost. Každý objekt výsledku má novou vlastnost přidána s názvem DeclarativeWebTestItemId, což je co se používá v kódu, chcete-li získat správnou žádost z testu výkonnosti webu.

```csharp
ExtractionRuleReference ruleReference = new ExtractionRuleReference();
     ruleReference.Type = typeof(ExtractText);
     ruleReference.ContextParameterName = "SessionId";
     ruleReference.Properties.Add(new PluginOrRuleProperty("EndsWith", "&ControlID="));
     ruleReference.Properties.Add(new PluginOrRuleProperty("HtmlDecode", "True"));
     ruleReference.Properties.Add(new PluginOrRuleProperty("IgnoreCase", "True"));
     ruleReference.Properties.Add(new PluginOrRuleProperty("Index", "0"));
     ruleReference.Properties.Add(new PluginOrRuleProperty("Required", "True"));
     ruleReference.Properties.Add(new PluginOrRuleProperty("StartsWith", "ReportSession="));
     ruleReference.Properties.Add(new PluginOrRuleProperty("UseRegularExpression", "False"));

     WebTestRequest requestInWebTest = e.RecordedWebTest.GetItem(page.DeclarativeWebTestItemId) as WebTestRequest;
     if (requestInWebTest != null)
     {
         requestInWebTest.ExtractionRuleReferences.Add(ruleReference);
         e.RecordedWebTestModified = true;
     }
```

## <a name="replace-query-string-parameters"></a>Nahrazení parametrů řetězce dotazu

Nyní kód vyhledá všechny dotaz parametrů řetězce, které mají ReportSession jako název a změňte hodnotu na {{SessionId}}, jak je znázorněno v této části Ukázky kódu:

```csharp
WebTestRequest requestInWebTest = e.RecordedWebTest.GetItem(page.DeclarativeWebTestItemId) as WebTestRequest;
if (requestInWebTest != null)
{
    foreach (QueryStringParameter param in requestInWebTest.QueryStringParameters)
    {
         if (param.Name.Equals("ReportSession"))
         {
             param.Value = "{{SessionId}}";
         }
     }
 }
```

```csharp
using System.ComponentModel;
using Microsoft.VisualStudio.TestTools.WebTesting;
using Microsoft.VisualStudio.TestTools.WebTesting.Rules;

namespace RecorderPlugin
{
    [DisplayName("Correlate ReportSession")]
    [Description("Adds extraction rule for Report Session and binds this to querystring parameters that use ReportSession")]
    public class CorrelateSessionId : WebTestRecorderPlugin
    {
        public override void PostWebTestRecording(object sender, PostWebTestRecordingEventArgs e)
        {
            //first find the session id
            bool foundId = false;
            foreach (WebTestResultUnit unit in e.RecordedWebTestResult.Children)
            {
                WebTestResultPage page = unit as WebTestResultPage;
                if (page != null)
                {
                    if (!foundId)
                    {
                        int indexOfReportSession = page.RequestResult.Response.BodyString.IndexOf("ReportSession");
                        if (indexOfReportSession > -1)
                        {
                            //add an extraction rule to this request
                            // Get the corresponding request in the Declarative Web performance test
                            ExtractionRuleReference ruleReference = new ExtractionRuleReference();

                            ruleReference.Type = typeof(ExtractText);
                            ruleReference.ContextParameterName = "SessionId";
                            ruleReference.Properties.Add(new PluginOrRuleProperty("EndsWith", "&ControlID="));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("HtmlDecode", "True"));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("IgnoreCase", "True"));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("Index", "0"));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("Required", "True"));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("StartsWith", "ReportSession="));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("UseRegularExpression", "False"));

                            WebTestRequest requestInWebTest = e.RecordedWebTest.GetItem(page.DeclarativeWebTestItemId) as WebTestRequest;
                            if (requestInWebTest != null)
                            {
                                requestInWebTest.ExtractionRuleReferences.Add(ruleReference);
                                e.RecordedWebTestModified = true;
                            }
                            foundId = true;

                        }
                    }
                    else
                    {
                        //now update query string parameters
                        WebTestRequest requestInWebTest = e.RecordedWebTest.GetItem(page.DeclarativeWebTestItemId) as WebTestRequest;
                        if (requestInWebTest != null)
                        {
                            foreach (QueryStringParameter param in requestInWebTest.QueryStringParameters)
                            {
                                if (param.Name.Equals("ReportSession"))
                                {
                                    param.Value = "{{SessionId}}";
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}
```

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin.PostWebTestRecording*>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRuleReference>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin.PostWebTestRecording*>
- [Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Generování a spuštění programového testu výkonnosti webu](../test/generate-and-run-a-coded-web-performance-test.md)
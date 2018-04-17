---
title: Přidání rozšíření protokolu jazyk serveru | Microsoft Docs
ms.custom: ''
ms.date: 11/14/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 52f12785-1c51-4c2c-8228-c8e10316cd83
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bb6c82eab6878e99c9840ed593d9b9993056d391
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-language-server-protocol-extension"></a>Přidání rozšíření protokolu jazyk serveru

Jazyk serveru protokolu (LSP) je společný protokol, ve tvaru v2.0 JSON RPC, používá k zajištění funkce služby pro různé editory kódu jazyka. Pomocí protokolu, mohou vývojáři psát jeden jazyk serveru zadejte jazyk funkce služby jako technologii IntelliSense, chyba diagnostiky, najít všechny odkazy, atd. pro různé editory kódu, které podporují LSP. Tradičně, můžete přidat jazyk služby v sadě Visual Studio a to buď pomocí souborů gramatika TextMate poskytnout základní funkce, například zvýraznění syntaxe, nebo vlastní jazyk služby pomocí úplné sady Visual Studio rozšiřitelnost rozhraní API pro zápis do Zadejte data širší. Nyní podpora LSP nabízí třetí možnost.

![Služba Protokol serveru jazyka v sadě Visual Studio](media/lsp-service-in-VS.png)

## <a name="language-server-protocol"></a>Jazyk serveru protokolu

Další informace o samotný protokol, najdete v dokumentaci [zde](https://github.com/Microsoft/language-server-protocol). Visual Studio implementace jazyk serveru protokolu je ve verzi preview a podpora by se měly zvažovat experimentální. Ve verzi preview je ve formě rozšíření ([jazyk serveru protokolu klienta ve verzi Preview](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)), **, ale tato rozšíření lze nainstalovat pouze na verze preview kanál ze sady Visual Studio**. Novější verze sady Visual Studio bude obsahovat integrovanou podporu pro jazyk serveru protokolu, po kterém se zahodí příznak Preview. **Pro produkční účely byste neměli používat verzi preview.**

Další informace o tom, jak vytvořit ukázkové jazyk serveru nebo jak integrovat existující server jazyk do Visual Studio Code, najdete v dokumentaci [zde](https://code.visualstudio.com/docs/extensions/example-language-server).

![Implementace protokolu jazyk serveru](media/lsp-implementation.png)

Tento článek popisuje postup vytvoření rozšíření sady Visual Studio, které používá jazyk LSP na server. Předpokládá, že jste již vytvořili serveru na základě LSP jazyk a chcete jen integrovat do sady Visual Studio.

Pro podporu v sadě Visual Studio můžete servery jazyk komunikaci s klientem (Visual Studio) pomocí následujících mechanismů:

* Standardní vstupní/výstupní datové proudy
* Pojmenované kanály
* Sokety

LSP a podpory pro něj v sadě Visual Studio je cílem zařadit jazyk služby, které nejsou součástí produktu Visual Studio. Rozhraní není určeno pro rozšíření stávající jazyk služeb (například C#) v sadě Visual Studio. Pokud chcete rozšířit existující jazyky, naleznete v příručce rozšiřitelnost služba jazyka (například [platformu kompilátoru .NET "Roslyn"](../extensibility/dotnet-compiler-platform-roslyn-extensibility.md)).

## <a name="language-server-protocol-features-supported"></a>Jazykové funkce serveru protokolu podporováno

Následující funkce LSP jsou podporovány v sadě Visual Studio, pokud:

Zpráva | Má podporu v sadě Visual Studio
--- | ---
Inicializace | Ano
inicializovat | Ano
vypnutí | Ano
Ukončení | Ano
$/ cancelRequest | Ano
okno nebo showMessage | Ano
okno nebo showMessageRequest | Ano
okno nebo logMessage | Ano
telemetrie/událost |
Klient nebo registerCapability |
Klient nebo unregisterCapability |
pracovní prostor nebo didChangeConfiguration | Ano
pracovní prostor nebo didChangeWatchedFiles | Ano
pracovní prostor nebo symbol | Ano
pracovní prostor nebo executeCommand | Ano
pracovní prostor nebo applyEdit | Ano
textDocument/publishDiagnostics | Ano
textDocument/didOpen | Ano
textDocument/didChange | Ano
textDocument/willSave |
textDocument/willSaveWaitUntil |
textDocument/didSave | Ano
textDocument/didClose | Ano
textDocument nebo dokončení | Ano
dokončení nebo řešení | Ano
textDocument/přechodu. | Ano
textDocument/signatureHelp | Ano
textDocument/odkazy | Ano
textDocument/documentHighlight |
textDocument/documentSymbol | Ano
textDocument nebo formátování | Ano
textDocument/rangeFormatting | Ano
textDocument/onTypeFormatting |
textDocument a definic | Ano
textDocument/codeAction | Ano
textDocument/Codelensu |
Codelensu nebo řešení |
textDocument/documentLink |
documentLink nebo řešení |
textDocument nebo přejmenování | Ano

## <a name="getting-started"></a>Začínáme

### <a name="create-a-vsix-project"></a>Vytvoření projektu VSIX

Vytvoření rozšíření služby jazyka pomocí serveru na základě LSP jazyk, nejdříve zajistěte, aby byla **vývoj rozšíření pro Visual Studio** zatížení pro vaše instance VS nainstalována.

Další přechodem na vytvoření nové prázdné VSIXProject **soubor** > **nový projekt** > **Visual C#**  >   **Rozšiřitelnost** > **projektu VSIX**:

![Vytvoření projektu vsix](media/lsp-vsix-project.png)

Ve verzi preview VS podpora LSP bude ve formě VSIX ([Microsoft.VisualStudio.LanguageServer.Client.Preview](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)). Rozšíření vývojáři, kteří chtějí vytvořit pomocí jazyka servery LSP rozšíření musí být závislý na tento VSIX. Proto zákazníci chtějí nainstalovat rozšíření serveru jazyk **musíte nejprve nainstalovat Preview VSIX jazyk serveru protokolu klienta.**

K definování závislostí VSIX, otevřete návrháře manifestu VSIX pro vaše VSIX (podle dvojitým kliknutím na soubor source.extension.vsixmanifest ve vašem projektu) a přejděte do **závislosti**:

![Přidat odkaz na jazyk serveru protokolu klienta](media/lsp-reference-lsp-dependency.png)

Vytvoření nové závislosti takto:

![Definovat jazyk serveru protokolu klienta závislostí](media/lsp-define-lsp-dependency.png)

* **Zdroj**: definované ručně
* **Název**: jazyk serveru protokolu klienta ve verzi Preview
* **Identifier**: Microsoft.VisualStudio.LanguageServer.Client.Preview
* **Rozsah verze**: [1.0,2.0)
* **Jak je vyřešit závislosti**: nainstalovaná uživatelem
* **Adresa URL pro stažení**: [https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)

> [!NOTE]
> **Stáhnout URL** musí být vyplněna, takže uživatelé, kteří instalují rozšíření vědět, jak nainstalovat požadované závislosti.

### <a name="language-server-and-runtime-installation"></a>Instalace serveru a prostředí runtime jazyka

Ve výchozím nastavení rozšíření vytvořili pro podporu serverů, na základě LSP jazyk v sadě Visual Studio nebude obsahovat samotné servery jazyk nebo moduly runtime potřebné k jejich vyřízení. Rozšíření vývojáři jsou zodpovědní za distribuci jazyka servery a moduly runtime potřeby. To udělat několika způsoby:

* Jazyk serverů může být vložen do VSIX jako soubory obsahu.
* Vytvoření souboru MSI pro instalaci serveru jazyk nebo potřeby moduly runtime.
* Poskytují pokyny na Marketplace informující uživatele, jak získat moduly runtime a jazyk servery.

### <a name="textmate-grammar-files"></a>Soubory TextMate – gramatika

LSP nezahrnuje specifikace o tom, jak poskytnout zabarvení text pro jazyky. Pokud chcete zadat vlastní zabarvení jazyků v sadě Visual Studio, rozšíření vývojáři mohou použít soubor gramatika TextMate. Pokud chcete přidat vlastní soubory TextMate gramatika nebo motiv, postupujte takto:

1. Vytvořte složku s názvem "Gramatika" uvnitř rozšíření (nebo může být jakýkoli název, který zvolíte).

2. V této složce "Gramatika" zahrnují *.tmlanguage, *.plist, *.tmtheme nebo *.json soubory, které byste chtěli, které poskytuje vlastní zabarvení.

3. Klikněte pravým tlačítkem na soubory a vyberte **vlastnosti**. Změňte akci sestavení na **obsahu** a **zahrnout do VSIX** vlastnost na hodnotu true.

4. Vytvořte soubor .pkgdef a podobně jako tento řádek:

  ```xml
  [$RootKey$\TextMate\Repositories]
  "MyLang"="$PackageFolder$\Grammars"
  ```

5. Klikněte pravým tlačítkem na soubory a vyberte **vlastnosti**. Změňte akci sestavení na **obsahu** a **zahrnout do VSIX** vlastnost na hodnotu true.

Po dokončení předchozích kroků, se přidá do složky "Gramatika" k instalaci balíčku adresáři jako zdrojové úložiště s názvem 'MyLang' ('MyLang' je právě název rozlišení více tras a může být libovolný jedinečný řetězec). Všechny gramatika (.tmlanguage soubory) a motiv soubory (.tmtheme) v tomto adresáři jsou zachyceny jako možnosti a mají přednost před předdefinované gramatika součástí TextMate. Pokud soubor gramatika deklarované rozšíření odpovídají na příponu souboru otevíráte, bude kroku TextMate.

## <a name="creating-a-simple-language-client"></a>Vytvoření jednoduchého jazyk klienta

### <a name="main-interface---ilanguageclientdotnetapimicrosoftvisualstudiolanguageserverclientilanguageclientviewvisualstudiosdk-2017"></a>Hlavní rozhraní - [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)

Po vytvoření projektu VSIX, přidejte následující balíčky NuGet do projektu:

* [Microsoft.VisualStudio.LanguageServer.Client](https://www.nuget.org/packages/Microsoft.VisualStudio.LanguageServer.Client)

> [!NOTE]
> Pokud převezmete závislost na balíček NuGet po dokončení předchozích kroků, balíčky Newtonsoft.Json a StreamJsonRpc jsou přidány do projektu také. **Nelze aktualizovat tyto balíčky, pokud si nejste jisti, že tyto nové verze bude nainstalována na verzi sady Visual Studio, vaše cíle rozšíření**. Sestavení nebudou zahrnuty ve vašem VSIX – místo toho se budou být zachyceny z instalačního adresáře nástroje Visual Studio. Pokud je odkazováno na novější verzi sestavení, než je nainstalována v počítači uživatele, rozšíření *nebude fungovat*.

Potom můžete vytvořit novou třídu, která implementuje [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017) rozhraní, hlavní rozhraní, které jsou potřebné pro jazyk klienti připojení k serveru na základě LSP jazyk.

Zde je ukázka:

```csharp
namespace MockLanguageExtension
{
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
        public string Name => "Bar Language Extension";

        public IEnumerable<string> ConfigurationSections => null;

        public object InitializationOptions => null;

        public IEnumerable<string> FilesToWatch => null;

        public event AsyncEventHandler<EventArgs> StartAsync;
        public event AsyncEventHandler<EventArgs> StopAsync;

        public async Task<Connection> ActivateAsync(CancellationToken token)
        {
            await Task.Yield();

            ProcessStartInfo info = new ProcessStartInfo();
            info.FileName = Path.Combine(Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location), "Server", @"MockLanguageServer.exe");
            info.Arguments = "bar";
            info.RedirectStandardInput = true;
            info.RedirectStandardOutput = true;
            info.UseShellExecute = false;
            info.CreateNoWindow = true;

            Process process = new Process();
            process.StartInfo = info;

            if (process.Start())
            {
                return new Connection(process.StandardOutput.BaseStream, process.StandardInput.BaseStream);
            }

            return null;
        }

        public async Task OnLoadedAsync()
        {
            await StartAsync?.InvokeAsync(this, EventArgs.Empty);
        }

        public async Task OnServerInitializeFailedAsync(Exception e)
        {
            return Task.CompletedTask;
        }

        public async Task OnServerInitializedAsync()
        {
            return Task.CompletedTask;
        }
    }
}
```

Hlavní metody, které potřebují k implementaci jsou [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) a [ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017). [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) je volána, když Visual Studio načetl rozšíření a jazyk server je připraven ke spuštění. U této metody můžete vyvolat [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) delegáta okamžitě na signál, že jazyk serveru by měl být spuštěn, nebo můžete provést další logiku a vyvolání [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) později. **Pokud chcete aktivovat jazyk serveru, musí volat StartAsync v určitém okamžiku.**

[ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017) je metoda nakonec vyvolat volání [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) delegovat; obsahuje logiku pro spuštění jazyk serveru a připojení k němu. Objekt připojení, která obsahuje datové proudy pro zápis do serveru a čtení ze serveru musí být vrácen. Jakékoli výjimky vydané tady jsou zachycení a zobrazí uživateli zprávu informačním panelu v sadě Visual Studio.

### <a name="activation"></a>Aktivace

Jakmile se implementuje třída jazyka klienta, budete muset definují dva atributy pro něj můžete definovat, jak bude načten do sady Visual Studio a aktivovat:

```csharp
  [Export(typeof(ILanguageClient))]
  [ContentType("bar")]
```

### <a name="mef"></a>MEF

Visual Studio použije [MEF](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) (spravované rozhraní rozšiřitelnosti) ke správě svých bodů rozšiřitelnosti. [Exportovat](https://msdn.microsoft.com/library/system.componentmodel.composition.exportattribute(v=vs.110).aspx) atribut označuje k sadě Visual Studio, že tato třída by měla být zachyceny jako bod rozšíření a načíst v příslušnou dobu.

Pokud chcete používat MEF, musí definovat také MEF jako prostředek v manifestu VSIX.

Otevřete si vaše návrháře manifestu VSIX a přejděte do **prostředky** karty:

![Přidat prostředek MEF](media/lsp-add-asset.png)

Klikněte na tlačítko Nový vytvořit nového prostředku:

![definování MEF asset](media/lsp-define-asset.png)

* **Typ**: Microsoft.VisualStudio.MefComponent
* **Zdroj**: na projekt v aktuálním řešení
* **Projekt**: [projektu]

### <a name="content-type-definition"></a>Definice typu obsahu

Aktuálně je jediný způsob, jak načíst rozšíření serveru na základě LSP jazyk podle typu obsahu souboru. To znamená při definování třída jazyk klienta (které implementuje [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)), budete muset určit typy souborů, je-li otevřít, způsobí, že rozšíření načíst. Pokud jsou otevřené žádné soubory, které odpovídají definované typ obsahu, nebude možné načíst rozšíření.

To se provádí prostřednictvím definování jednu nebo více tříd ContentTypeDefinition:

```csharp
namespace MockLanguageExtension
{
    public class BarContentDefinition
    {
        [Export]
        [Name("bar")]
        [BaseDefinition(CodeRemoteContentDefinition.CodeRemoteContentTypeName)]
        internal static ContentTypeDefinition BarContentTypeDefinition;


        [Export]
        [FileExtension(".bar")]
        [ContentType("bar")]
        internal static FileExtensionToContentTypeDefinition BarFileExtensionDefinition;
    }
}
```

V předchozím příkladu se vytvoří definici typu obsahu pro soubory, které končí `.bar` příponu souboru. Definice pro typ obsahu, který je uveden název "řádku" a **musí** odvozena od [CodeRemoteContentTypeName](/dotnet/api/microsoft.visualstudio.languageserver.client.coderemotecontentdefinition.coderemotecontenttypename?view=visualstudiosdk-2017).

Po přidání definici typu obsahu, můžete pak definovat, kdy se mají načíst rozšíření jazyk klienta ve třídě jazyk klienta:

```csharp
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
    }
```

Přidání podpory pro servery jazyk LSP nevyžaduje, abyste implementovat vlastní systému projektu v sadě Visual Studio. Zákazníci, můžete otevřít v sadě Visual Studio k použití služby jazyk jeden soubor nebo složku. Ve skutečnosti podporovat pro servery LSP jazyk je navržen pro práci jenom v situacích, otevřete složka či soubor. Pokud se implementuje systému vlastní projektu, některé funkce (například nastavení) nebude fungovat.

## <a name="advanced-features"></a>Pokročilé funkce

### <a name="settings"></a>Nastavení

Podpora pro vlastní nastavení pro konkrétní jazyk serveru je k dispozici pro verzi Preview LSP podpory v sadě Visual Studio, ale je stále ještě probíhá zlepšila. Nastavení jsou specifická pro co serveru jazyk podporuje a obvykle řídit, jak jazyk serveru vysílá data. Například jazyk serveru může mít nastavení pro maximální počet ohlášených chyb. Rozšíření autoři by definovat výchozí hodnotu, která může změnit uživatele pro konkrétní projekty.

Pomocí těchto kroků-li přidat podporu pro nastavení služby linky LSP jazyka:

1. Přidejte soubor JSON (například "MockLanguageExtensionSettings.json") ve vašem projektu, který obsahuje nastavení a výchozí hodnoty. Příklad:

  ```json
  {
    "foo.maxNumberOfProblems": -1
  }
  ```
2. Klikněte pravým tlačítkem na soubor JSON a vyberte **vlastnosti**. Změna **sestavení** akce na "Obsah" a "zahrnout do VSIX' vlastnost na hodnotu true.

3. Implementace oddíly ConfigurationSections a vrátí seznam předpon pro nastavení definované v souboru JSON (ve Visual Studio Code, to by mapovat název konfiguračního oddílu v souboru package.json):

  ```csharp
  public IEnumerable<string> ConfigurationSections
  {
      get
      {
          yield return "foo";
      }
  }
  ```
4. Přidejte do projektu soubor .pkgdef (Přidat nový textový soubor a změňte příponu souboru na .pkgdef). Soubor pkgdef by měl obsahovat tyto informace:

  ```xml
    [$RootKey$\OpenFolder\Settings\VSWorkspaceSettings\[settings-name]]
    @="$PackageFolder$\[settings-file-name].json"
  ```

5. Klikněte pravým tlačítkem na soubor .pkgdef a vyberte **vlastnosti**. Změna **sestavení** akce "Obsah" a "Zahrnují v VSIX" vlastnost na hodnotu true.

6. Otevřete `source.extension.vsixmanifest` souboru a přidat prostředek v **Asset** karty:

  ![Upravit prostředek vspackage](media/lsp-add-vspackage-asset.png)

  * **Typ**: Microsoft.VisualStudio.VsPackage
  * **Zdroj**: souboru v systému souborů
  * **Cesta**: [cesta k souboru pkgdef]

### <a name="user-editing-of-settings-for-a-workspace"></a>Uživatel upravuje nastavení pro pracovní prostor

1. Uživatel otevře obsahující soubory, které patří server pracovního prostoru.
2. Uživatel přidá do souboru ve složce "neodstraňujte" názvem "VSWorkspaceSettings.json".
3. Uživatel přidá řádek do souboru VSWorkspaceSettings.json pro nastavení, které poskytuje server. Příklad:

  ```json
  {
    "foo.maxNumberOfProblems": 10
  }
  ```
### <a name="enabling-diagnostics-tracing"></a>Povolení trasování diagnostiky
K vypsání všech zpráv mezi klientem a serverem, které mohou být užitečné při ladění problémů se dá zapnout diagnostické trasování.  Pokud chcete povolit diagnostické trasování, postupujte takto:

1. Otevřít nebo vytvořit soubor s nastaveními prostoru "VSWorkspaceSettings.json" (viz "Uživatelské úpravy nastavení pracovního prostoru").
2. Přidejte následující řádek v souboru json nastavení:

```json
{
    "foo.server.trace": "Off"
}
```

Existují tři možné hodnoty pro trasování podrobností:
* "Off": zcela vypnout trasování
* "Zprávy": budou trasovány trasování zapnutá, ale ID jedinou metodou název a odpovědi.
* "Podrobné": trasování zapnuto; zpráva celý rpc je trasovat.

Pokud je trasování zapnutý obsah se zapisují do souboru v adresáři "% temp%\VisualStudio\LSP".  Protokol následuje formát pojmenování `[LanguageClientName]-[Datetime Stamp].log`.  V současné době může trasování povoleno pouze pro scénáře otevřít složku.  Otevírání jeden soubor k aktivaci serveru jazyk nemá diagnostické trasování podpory.

### <a name="custom-messages"></a>Vlastní zprávy

Existují rozhraní API v místě pro usnadnění předávání zpráv a příjmu zprávy ze serveru pro jazyk, které nejsou součástí protokolu standardní jazyk serveru. Zpracování vlastních zpráv, implementovat [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) rozhraní v třídě jazyk klienta. [VS-StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) knihovna se používá k přenosu vlastního zpráv mezi jazyk klienta a serveru jazyk. Vzhledem k tomu, že rozšíření LSP jazyk klienta je stejně jako ostatní rozšíření sady Visual Studio, můžete rozhodnete přidat další funkce, (které nejsou podporované LSP) pro Visual Studio (pomocí rozhraní API jiných Visual Studio) ve vašem rozšíření prostřednictvím vlastních zpráv.

#### <a name="receiving-custom-messages"></a>Přijímání vlastní zpráv

Aby se vlastní zprávy ze serveru pro jazyk, implementovat [CustomMessageTarget](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.custommessagetarget?view=visualstudiosdk-2017) vlastnost na [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) a vrátí objekt, který umí pro zpracování vlastních zpráv . Následující příklad:

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public object CustomMessageTarget
    {
        get;
        set;
    }

    public class CustomTarget
    {
        public void OnCustomNotification(JToken arg)
        {
            // Provide logic on what happens OnCustomNotification is called from the language server
        }

        public string OnCustomRequest(string test)
        {
            // Provide logic on what happens OnCustomRequest is called from the language server
        }
    }
}
```

#### <a name="sending-custom-messages"></a>Odesílání vlastní zpráv

Pokud chcete odeslat vlastní zprávy do serveru jazyk, implementovat [AttachForCustomMessageAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.attachforcustommessageasync?view=visualstudiosdk-2017) metodu [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017). Tato metoda je voláno, když je váš jazyk server spuštěn a přijímat zprávy. A [JsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/src/StreamJsonRpc/JsonRpc.cs) objekt je předán jako parametr, který potom můžete zachovat k odesílání zpráv do serveru jazyka pomocí [VS-StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) rozhraní API. Následující příklad:

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public async Task AttachForCustomMessageAsync(JsonRpc rpc)
    {
        await Task.Yield();

        this.customMessageRpc = rpc;
    }

    public async Task SendServerCustomNotification(object arg)
    {
        await this.customMessageRpc.NotifyWithParameterObjectAsync("OnCustomNotification", arg);
    }

    public async Task<string> SendServerCustomMessage(string test)
    {
        return await this.customMessageRpc.InvokeAsync<string>("OnCustomRequest", test);
    }
}
```

### <a name="middle-layer"></a>Střední vrstva

Někdy vývojář rozšíření chtít zachytit LSP zprávy odesílané do a ze serveru jazyk. Například může vývojář rozšíření chcete změnit parametr zprávy odeslané konkrétní LSP zprávy nebo upravit výsledky vrácené ze serveru jazyk pro funkce LSP (například dokončených). Pokud je to nezbytné, vývojáři rozšíření můžete použít rozhraní API MiddleLayer zachytávat LSP zprávy.

Každá zpráva LSP má svou vlastní střední vrstvu rozhraní pro zachycení. K zachycení konkrétní zprávy, vytvořte třídu, která implementuje rozhraní prostřední vrstva pro tuto zprávu. Potom implementovat [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) rozhraní v třídě jazyk klienta a vrátit instanci objektu v [MiddleLayer](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.middlelayer?view=visualstudiosdk-2017) vlastnost. Následující příklad:

```csharp
public class MockLanguageClient: ILanguageClient, ILanguageClientCustomMessage
{
    public object MiddleLayer => MiddleLayerProvider.Instance;

    private class MiddleLayerProvider : ILanguageClientWorkspaceSymbolProvider
    {
        internal readonly static MiddleLayerProvider Instance = new MiddleLayerProvider();

        private MiddleLayerProvider()
        {
        }

        public async Task<SymbolInformation[]> RequestWorkspaceSymbols(WorkspaceSymbolParams param, Func<WorkspaceSymbolParams, Task<SymbolInformation[]>> sendRequest)
        {
            // Send along the request as given
            SymbolInformation[] symbols = await sendRequest(param);

            // Only return symbols that are "files"
            return symbols.Where(sym => string.Equals(new Uri(sym.Location.Uri).Scheme, "file", StringComparison.OrdinalIgnoreCase)).ToArray();
        }
    }
}
```

Funkce střední vrstvy, je stále ve vývoji a ještě komplexní.

## <a name="sample-lsp-language-server-extension"></a>Ukázka LSP jazyk serveru rozšíření

Pokud chcete zobrazit zdrojový kód Ukázka rozšíření pomocí klienta LSP rozhraní API v sadě Visual Studio, najdete v části Ukázky rozšiřitelnosti VSSDK [LSP ukázka](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/LanguageServerProtocol).

## <a name="faq"></a>Nejčastější dotazy

**Nastavit jako k vytváření vlastních projektů systému doplníte Moje LSP jazyk serveru poskytovat bohatší podporu funkce v sadě Visual Studio, jak postupovat učinit?**

Podpora pro servery, na základě LSP jazyk v sadě Visual Studio využívá [funkce Otevřít složku](https://blogs.msdn.microsoft.com/visualstudio/2016/04/12/open-any-folder-with-visual-studio-15-preview/) a je určená speciálně pro nevyžadují systému vlastní projektu. Můžete vytvořit vlastní projekt systému pokynů [zde](https://github.com/Microsoft/VSProjectSystem), ale některé funkce, jako je například nastavení, nemusí fungovat. Výchozí inicializace logiku pro servery LSP jazyk je předávat složky, do kořenové složky aktuálně otevíráte, takže pokud používáte vlastní projekt systému, budete muset během inicializace zajistit jazyk serveru můžete zadat vlastní logiky správně spusťte.

**Jak přidat podporu ladicí program?**

Jsme zajištění podpory u [běžné ladění protokolu](https://code.visualstudio.com/docs/extensionAPI/api-debugging) v budoucí verzi.

**Pokud je již VS podporované jazykové služby nainstalovat (například JavaScript), lze přesto nainstalovat LSP jazyk serveru rozšíření, která nabízí další funkce, (například linting)?**

Ano, ale ne všechny funkce budou fungovat správně. Konečným cílem pro LSP jazyk serveru rozšíření je pro povolení služby jazyk není nativně podporované Visual Studio. Můžete vytvořit rozšíření, která nabízí další podporu pomocí LSP jazyk serverů, ale některé funkce (například IntelliSense) nebude smooth prostředí. Obecně se doporučuje, aby LSP jazyk serverová rozšíření aplikace lze použít k poskytnutí nové možnosti jazyk není rozšíření stávajících.

**Kde lze publikovat Moje dokončené jazyk serveru LSP VSIX?**

Postupujte podle pokynů Marketplace [zde](walkthrough-publishing-a-visual-studio-extension.md).

---
title: Přidání rozšíření protokol jazyka serveru | Dokumentace Microsoftu
ms.date: 11/14/2017
ms.topic: conceptual
ms.assetid: 52f12785-1c51-4c2c-8228-c8e10316cd83
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d9b268c0c15ce468ca40a90583c5b7310364c189
ms.sourcegitcommit: 283f2dbce044a18e9f6ac6398f6fc78e074ec1ed
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/16/2019
ms.locfileid: "65805117"
---
# <a name="add-a-language-server-protocol-extension"></a>Přidat příponu protokol jazyka serveru

Protokol jazyka serveru (LSP) je společný protokol ve formátu JSON RPC v2.0, používají k zajištění funkce služby pro různé editory kódu jazyka. Pomocí protokolu, můžou vývojáři psát, že jeden jazyk serveru, který poskytuje služba jazyka funkce jako IntelliSense, Diagnostika chyb najít všechny odkazy a tak dále, pro různé editory kódu, které podporují LSP. Tradičně jazykových služeb v sadě Visual Studio lze přidat pomocí souborů gramatiky TextMate poskytnout základní funkce, jako jsou zvýraznění syntaxe nebo zápisem vlastního jazykovými službami, které umožňuje poskytují kompletní sadu rozhraní API pro rozšíření sady Visual Studio Podrobnější údaje. S Visual Studio – podpora pro LSP je třetí možnost.

![Služba Protokol jazyka serveru v sadě Visual Studio](media/lsp-service-in-VS.png)

## <a name="language-server-protocol"></a>Protokol jazyka serveru

![implementaci protokol jazyka serveru](media/lsp-implementation.png)

Tento článek popisuje, jak vytvořit rozšíření sady Visual Studio, který využívá jazyk na základě LSP server. Předpokládá, že server služby jazyka založeného na LSP už vytváříte a chcete jenom ji integrovat do sady Visual Studio.

Pro podporu Visual Studia jazyk servery můžou klienti komunikovat klienta (Visual Studio) prostřednictvím každý použitý mechanizmus na základě datového proudu přenosu, například:

* Standardní vstupní/výstupní datové proudy
* Pojmenované kanály
* Sokety (pouze TCP)

Záměrem LSP a podporu v sadě Visual Studio je připojení jazykovými službami, které nejsou součástí produktu Visual Studio. Má nejsou určeny k rozšíření stávající služby jazyka (například C#) v sadě Visual Studio. Rozšířit existující jazyky, najdete v tématu Průvodce rozšíření služeb jazyka (například [platformě .NET Compiler Platform "Roslyn"](../extensibility/dotnet-compiler-platform-roslyn-extensibility.md)).

Další informace o samotný protokol, naleznete v dokumentaci [tady](https://github.com/Microsoft/language-server-protocol).

Další informace o tom, jak vytvořit ukázkový server jazyka nebo jak integrovat existující server jazyk do Visual Studio Code, naleznete v dokumentaci [tady](https://code.visualstudio.com/docs/extensions/example-language-server).

## <a name="language-server-protocol-supported-features"></a>Protokol jazyka serveru podporované funkce

Následující tabulka ukazuje LSP funkcí, které jsou podporovány v sadě Visual Studio:

Message | Má podporu v sadě Visual Studio
--- | ---
Inicializace | ano
inicializován | ano
vypnutí | ano
ukončení | ano
$/ cancelRequest | ano
okno/Zobrazitzpravu | ano
okno/showMessageRequest | ano
window/logMessage | ano
telemetrie a událostí |
client/registerCapability |
client/unregisterCapability |
workspace/didChangeConfiguration | ano
workspace/didChangeWatchedFiles | ano
pracovní prostor/symbol | ano
pracovní prostor/executeCommand | ano
pracovní prostor/applyEdit | ano
textDocument/publishDiagnostics | ano
textDocument/didOpen | ano
textDocument/didChange | ano
textDocument/willSave |
textDocument/willSaveWaitUntil |
textDocument/didSave | ano
textDocument/didClose | ano
textDocument/dokončení | ano
dokončení nebo řešení | ano
textDocument/hover | ano
textDocument/signatureHelp | ano
textDocument/odkazy | ano
textDocument/documentHighlight | ano
textDocument/documentSymbol | ano
textDocument/formátování | ano
textDocument/rangeFormatting | ano
textDocument/onTypeFormatting |
textDocument/definici | ano
textDocument/codeAction | ano
textDocument/codeLens |
codeLens/resolve |
textDocument/documentLink |
documentLink/resolve |
textDocument/přejmenování | ano

## <a name="get-started"></a>Začínáme

> [!NOTE]
> Od verze Visual Studio 2017 verze 15.8, podpora pro běžné protokol jazyka serveru je integrovaná do sady Visual Studio. Pokud jste vytvořili LSP rozšíření pomocí verze preview [jazyk serveru klienta VSIX](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview) verze, přestanou fungovat po upgradu na verzi 15,8 nebo vyšší. Budete muset následujícím postupem získejte rozšíření LSP znovu pracovat:
>
> 1. Odinstalujte Microsoft Visual Studio jazyk serveru protokolu Preview VSIX.
>
>    Počínaje verzí 15.8, pokaždé, když provedete upgrade v sadě Visual Studio preview VSIX je automaticky zjistil a odebrat.
>
> 2. Aktualizujte referenci Nuget na nejnovější verzi – ve verzi preview pro [LSP balíčky](https://www.nuget.org/packages/Microsoft.VisualStudio.LanguageServer.Client).
>
> 3. Odeberte závislost na Microsoft Visual Studio jazyka serveru protokolu ve verzi Preview VSIX v manifestu VSIX.
>
> 4. Ujistěte se, že VSIX určuje Visual Studio 2017 verze 15.8 3 ve verzi Preview jako dolní mez pro cíl instalace.
>
> 5. Znovu sestavte a znovu nasadit.

### <a name="create-a-vsix-project"></a>Vytvořte projekt VSIX

Chcete-li vytvořit rozšíření služeb jazyka pomocí serveru jazyk na základě LSP, nejprve ujistěte se, že máte **vývoj rozšíření sady Visual Studio** nainstalovaná pro vaši instanci VS úloha.

Dále vytvořte nový projekt VSIX tak, že přejdete do **souboru** > **nový projekt** > **Visual C#**   >  **Rozšiřitelnost** > **projekt VSIX**:

![Vytvoření projektu vsix](media/lsp-vsix-project.png)

### <a name="language-server-and-runtime-installation"></a>Instalace jazyků serveru a modulu runtime

Ve výchozím nastavení rozšíření vytvořili za účelem podpory jazyka založeného na LSP servery v sadě Visual Studio neobsahují samotné servery jazyka nebo modulů runtime potřebné ke spuštění je. Vývojáři rozšíření jsou odpovídá za distribuci servery jazyka a moduly runtime potřeba. Chcete-li to provést několika způsoby:

* Jazyk serverů může být vložen do VSIX jako soubory obsahu.
* Vytvořit soubor MSI instalace serveru pro jazyk a/nebo potřeby moduly runtime.
* Pokyny na webu Marketplace informující uživatele získání servery moduly runtime a jazyk.

### <a name="textmate-grammar-files"></a>Soubory gramatiky TextMate

LSP neobsahuje specifikaci o tom, jak poskytnout zabarvení textu pro jazyky. Pokud chcete zadat vlastní barevné zvýraznění pro jazyky v sadě Visual Studio, vývojáři rozšíření můžete použít soubor gramatiky TextMate. Chcete-li přidat vlastní soubory TextMate gramatiky nebo motivu, postupujte takto:

1. Vytvořte složku s názvem "Gramatiky" uvnitř rozšíření (nebo může být jakýkoli název, který zvolíte).

2. Uvnitř *gramatiky* složky, zahrnutí všech  *\*.tmlanguage*,  *\*.plist*,  *\*.tmtheme*, nebo  *\*.json* chcete soubory, které poskytují vlastní zabarvení.

   > [!TIP]
   > A *.tmtheme* soubor definuje, jak jsou obory mapovaná na klasifikace sady Visual Studio (s názvem klíče barvu). Pokyny, můžete odkazovat globální *.tmtheme* soubor *% ProgramFiles (x86) %\Microsoft Visual Studio\\\<verze >\\\<SKU > \Common7\ IDE\CommonExtensions\Microsoft\TextMate\Starterkit\Themesg* adresáře.

3. Vytvoření *.pkgdef* soubor a přidá řádek podobný tomuto:

    ```
    [$RootKey$\TextMate\Repositories]
    "MyLang"="$PackageFolder$\Grammars"
    ```

4. Klikněte pravým tlačítkem na požadované soubory, vyberte **vlastnosti**. Změnit **sestavení** akce **obsahu** a změnit **zahrnout do VSIX** vlastnost **true**.

Po dokončení předchozích kroků *gramatiky* přidat složku k instalaci balíčku adresář jako zdrojové úložiště s názvem 'MyLang' ("MyLang" je pouze název pro odstraňování mnohoznačnosti a může obsahovat libovolný jedinečný řetězec). Všechny gramatiku (*.tmlanguage* soubory) a soubory motivů (*.tmtheme* souborů) v tomto adresáři, vyberou se jako možnosti a mají přednost před integrované gramatik TextMate součástí. Pokud soubor gramatiky deklarované rozšíření odpovídají příponám souborů otevírané, TextMate přesune se krokování.

## <a name="create-a-simple-language-client"></a>Vytvořte Jednoduchý jazyk klienta

### <a name="main-interface---ilanguageclientdotnetapimicrosoftvisualstudiolanguageserverclientilanguageclientviewvisualstudiosdk-2017"></a>Hlavní rozhraní - [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)

Po vytvoření projektu VSIX, přidejte následující balíčky NuGet do projektu:

* [Microsoft.VisualStudio.LanguageServer.Client](https://www.nuget.org/packages/Microsoft.VisualStudio.LanguageServer.Client)

> [!NOTE]
> Když zavést závislost na balíčku NuGet. Po dokončení předchozích kroků, Newtonsoft.Json a StreamJsonRpc balíčky přidají do svého projektu také. **Pokud si nejste jisti, že tyto nové verze se nainstaluje na verzi sady Visual Studio neaktualizují tyto balíčky, které vaše rozšíření cílí**. Sestavení se nezahrnuly do VSIX; Místo toho se vybere si z adresáře instalace sady Visual Studio. Pokud odkazujete na novější verzi sestavení, než jaká je nainstalována v počítači uživatele, nebude vaše rozšíření fungovat.

Potom můžete vytvořit novou třídu, která implementuje [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017) rozhraní, které představuje hlavní rozhraní potřebné pro připojení k serveru jazyk na základě LSP klienty jazyka.

Tady je ukázka:

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
            await StartAsync.InvokeAsync(this, EventArgs.Empty);
        }

        public Task OnServerInitializeFailedAsync(Exception e)
        {
            return Task.CompletedTask;
        }

        public Task OnServerInitializedAsync()
        {
            return Task.CompletedTask;
        }
    }
}
```

Hlavní metody, které je třeba k implementaci jsou [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) a [ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017). [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) se volá při načtení rozšíření sady Visual Studio a jazyka serveru je připraven ke spuštění. V této metodě, můžete vyvolat [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) okamžitě na signál, že jazyk serveru měly být spuštěny, nebo můžete provést další logiku a vyvolání delegáta [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) později. **K aktivaci serveru jazyk, je nutné volat StartAsync v určitém okamžiku.**

[ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017) je metoda nakonec vyvolána voláním [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) delegovat. Obsahuje logiku pro spuštění jazyk serveru a připojení k němu. Objekt připojení, který obsahuje datové proudy pro zápis do serveru a čtení ze serveru musí být vrácena. Jakýchkoli výjimek jsou zachyceny a zobrazí uživateli zprávou informační panel v sadě Visual Studio.

### <a name="activation"></a>Aktivace

Jakmile je třída jazyka klienta, budete muset definovat dva atributy, aby se definovat, jak ho načíst do sady Visual Studio, který se aktivuje:

```csharp
  [Export(typeof(ILanguageClient))]
  [ContentType("bar")]
```

### <a name="mef"></a>MEF

Visual Studio používá [MEF](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) (Managed Extensibility Framework) ke správě svých bodů rozšiřitelnosti. [Exportovat](/dotnet/api/system.componentmodel.composition.exportattribute) atribut označuje do sady Visual Studio, že tato třída nenačítají jako rozšiřovacím bodem a načíst v příslušnou dobu.

Použití rozhraní MEF, musíte také definovat MEF jako prostředek v manifestu VSIX.

Otevřete návrháře manifestu VSIX a přejděte **prostředky** kartu:

![Přidat prostředek MEF](media/lsp-add-asset.png)

Klikněte na tlačítko **nový** k vytvoření nového prostředku:

![definování MEF asset](media/lsp-define-asset.png)

* **Typ**: Microsoft.VisualStudio.MefComponent
* **Zdroj**: Projekt v aktuálním řešení
* **Projekt**: [projekt]

### <a name="content-type-definition"></a>Definice typu obsahu

V současné době je jediný způsob, jak načíst vaše rozšíření jazyka založeného na LSP serveru podle typu obsahu souboru. To znamená při definování třída klienta jazyk (která implementuje [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)), budete muset určit typy souborů, které, je-li otevřít, způsobí, že rozšíření pro načtení. Pokud jsou otevřené žádné soubory, které odpovídají definované typ obsahu, pak vaše rozšíření se nenačte.

To se provádí prostřednictvím definuje jeden nebo více `ContentTypeDefinition` třídy:

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

V předchozím příkladu se vytvoří definice typu obsahu pro soubory, které končí *.bar* příponu souboru. Definice typu obsahu je uveden název "panel" a musí být odvozen od [CodeRemoteContentTypeName](/dotnet/api/microsoft.visualstudio.languageserver.client.coderemotecontentdefinition.coderemotecontenttypename?view=visualstudiosdk-2017).

Po přidání definice typu obsahu, pak můžete definovat, kdy se má načíst rozšíření jazyka klienta ve třídě jazyk klienta:

```csharp
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
    }
```

Přidání podpory pro LSP jazyk servery není nutné implementovat systém projektu v sadě Visual Studio. Zákazníci můžou otevřít jeden soubor nebo složku v sadě Visual Studio, pokud chcete začít používat služby jazyka. Ve skutečnosti podpora serverů LSP jazyk je navržen pro práci jenom v situacích, otevřít složku nebo soubor. Pokud je implementovaná vlastní projektový systém, nebudou fungovat některé funkce (například nastavení).

## <a name="advanced-features"></a>Pokročilé funkce

### <a name="settings"></a>Nastavení

Podpora pro vlastní nastavení pro konkrétní jazyk serveru je k dispozici, ale je stále probíhá proces jeho vylepšuje. Nastavení jsou specifická pro co server jazyk podporuje a obvykle řídí, jak jazyk serveru generuje data. Například jazyk serveru může mít nastavení pro maximální počet chyb zaznamenaný. Autoři rozšíření byste definovali výchozí hodnotu, která může změnit uživatele pro konkrétní projekty.

Postupujte podle následujících kroků pro přidání podpory pro nastavení rozšíření služeb jazyka LSP:

1. Přidání souboru JSON (například *MockLanguageExtensionSettings.json*) do projektu, který obsahuje nastavení a jejich výchozí hodnoty. Příklad:

    ```json
    {
        "foo.maxNumberOfProblems": -1
    }
    ```

2. Klikněte pravým tlačítkem na soubor JSON a vyberte **vlastnosti**. Změnit **sestavení** akce "Obsah" a "zahrnout do VSIX' vlastnost **true**.

3. Implementace oddíly ConfigurationSections a vrátí seznam předpon pro nastavení definované v souboru JSON (v aplikaci Visual Studio Code, to by namapovat na název oddílu konfigurace v souboru package.json):

    ```csharp
    public IEnumerable<string> ConfigurationSections
    {
        get
        {
            yield return "foo";
        }
    }
    ```

4. Soubor .pkgdef přidejte do projektu (Přidat nový textový soubor a změňte příponu souboru .pkgdef). Soubor pkgdef by měl obsahovat tyto informace:

    ```
    [$RootKey$\OpenFolder\Settings\VSWorkspaceSettings\[settings-name]]
    @="$PackageFolder$\[settings-file-name].json"
    ```

    Ukázka:

    ```
    [$RootKey$\OpenFolder\Settings\VSWorkspaceSettings\MockLanguageExtension]
    @="$PackageFolder$\MockLanguageExtensionSettings.json"
    ```

5. Klikněte pravým tlačítkem na soubor .pkgdef a vyberte **vlastnosti**. Změnit **sestavení** akce **obsahu** a **zahrnout do VSIX** vlastnost **true**.

6. Otevřete *source.extension.vsixmanifest* a přidejte prostředek **Asset** kartu:

   ![Upravit prostředek balíčku vspackage](media/lsp-add-vspackage-asset.png)

   * **Typ**: Microsoft.VisualStudio.VsPackage
   * **Zdroj**: Soubor v systému souborů
   * **Cesta**: [cesta k vaší *.pkgdef* souborů]

### <a name="user-editing-of-settings-for-a-workspace"></a>Uživatel upravuje nastavení pro pracovní prostor

1. Uživatel otevře pracovní prostor obsahující soubory, které je vlastníkem vašeho serveru.
2. Uživatel přidá soubor v *.vs* složku s názvem *VSWorkspaceSettings.json*.
3. Uživatel přidá řádek do *VSWorkspaceSettings.json* soubor pro třídu setting server poskytuje. Příklad:

    ```json
    {
        "foo.maxNumberOfProblems": 10
    }
    ```

### <a name="enable-diagnostics-tracing"></a>Povolení trasování diagnostiky

Diagnostické trasování je možné zapnout na výstup všech zpráv mezi klientem a serverem, který může být užitečné při ladění problémů. Pokud chcete povolit diagnostické trasování, postupujte takto:

1. Otevření nebo vytvoření souboru nastavení pracovního prostoru *VSWorkspaceSettings.json* (viz "Uživatel upravuje nastavení pro pracovní prostor").
2. Přidejte následující řádek v souboru nastavení json:

```json
{
    "foo.trace.server": "Off"
}
```

Existují tři možné hodnoty pro trasovacího podrobnosti:

* "Off": úplně vypnout trasování
* "Zprávy": trasování zapnuté, ale ID názvu a odpovědi pouze metody jsou trasovány.
* "Verbose": trasování zapnuté; zpráva rpc celý trasován.

Pokud je trasování zapnuto obsah se zapisují do souboru v *%temp%\VisualStudio\LSP* adresáře. Protokol formát pojmenování *[LanguageClientName]-[razítko data a času] log*. V současné době můžete trasování povoleno pouze pro otevřenou složku. Otevření jednoho souboru aktivace jazyk serveru nemá žádné diagnostické trasování podpory.

### <a name="custom-messages"></a>Vlastní zprávy

Rozhraní API na místě pro usnadnění předávání zpráv a přijímání zpráv ze serveru jazyka, které nejsou součástí standardní protokol jazyka serveru nejsou k dispozici. Pro zpracování vlastní zprávy, implementovat [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) rozhraní ve třídě jazyk klienta. [VS-StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) knihovna se používá k přenosu vlastního zpráv mezi jazyk klienta a serveru jazyka. Rozšíření LSP jazyk klienta je stejně jako ostatní rozšíření sady Visual Studio, můžete přidat další funkce, (, které nejsou podporované LSP) do sady Visual Studio (s použitím jiných Visual Studio rozhraní API) v rozšíření prostřednictvím vlastních zpráv.

#### <a name="receive-custom-messages"></a>Vlastní zprávy

Chcete-li vlastní zprávy ze serveru pro jazyk, implementovat [CustomMessageTarget](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.custommessagetarget?view=visualstudiosdk-2017) vlastnost [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) a vrátí objekt, který umí zpracovat vlastní zprávy . Následující příklad:

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

#### <a name="send-custom-messages"></a>Odeslat vlastní zprávy

Chcete-li odeslat vlastní zprávy na language server, implementovat [AttachForCustomMessageAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.attachforcustommessageasync?view=visualstudiosdk-2017) metoda [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017). Tato metoda vyvolána, když je váš jazyk server spuštěn a připravený pro příjem zpráv. A [JsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/src/StreamJsonRpc/JsonRpc.cs) objekt je předán jako parametr, který potom můžete ponechat pro odesílání zpráv do serveru pomocí jazyka [VS StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) rozhraní API. Následující příklad:

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

Vývojář rozšíření může někdy chcete zachytit LSP zprávy odesílané do a ze serveru pro jazyk. Vývojář rozšíření může například chcete změnit zprávu parametru odeslaného příslušné LSP zprávy nebo upravit výsledky vrácené ze serveru jazyk pro funkci LSP (například dokončování). Pokud je to nezbytné, rozšíření mohou vývojáři MiddleLayer API zachytit LSP zprávy.

Každá zpráva LSP má svůj vlastní střední vrstvu rozhraní pro zachycení. Aby se zachytily určité zprávy, vytvořte třídu, která implementuje rozhraní prostřední vrstva pro tuto zprávu. Pak implementovat [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) rozhraní ve třídě jazyk klienta a vrátit instanci objektu v [MiddleLayer](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.middlelayer?view=visualstudiosdk-2017) vlastnost. Následující příklad:

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

Funkce prostřední vrstva je stále ve vývoji a ještě nejsou úplné.

## <a name="sample-lsp-language-server-extension"></a>Rozšíření ukázky LSP jazyka serveru

Zdrojový kód ukázkové rozšíření pomocí rozhraní API klienta LSP v sadě Visual Studio najdete v tématu ukázky rozšiřitelnosti VSSDK [LSP ukázka](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/LanguageServerProtocol).

## <a name="faq"></a>Nejčastější dotazy

**Chci vytvořit vlastní projekt systém k doplnění LSP jazyk serveru k poskytování bohatších podporovaných funkcích v sadě Visual Studio, jak se mám obrátit o to provedete?**

Podpora jazyka založeného na LSP serverů v sadě Visual Studio využívá [funkce Otevřít složku](https://devblogs.microsoft.com/visualstudio/open-any-folder-with-visual-studio-15-preview/) a je navržen tak, aby nebyl vyžadován vlastní projektový systém. Můžete vytvářet vlastní projekt systému postupujte podle pokynů [tady](https://github.com/Microsoft/VSProjectSystem), ale některé funkce, jako je například nastavení, nemusí fungovat. Výchozí inicializace logiku pro servery LSP jazyka je a zajistěte tak předání složky, do kořenové složky je aktuálně otevřenou, takže pokud používáte vlastní projektový systém, budete muset poskytnout vlastní logiku během inicializace k zajištění můžete server language správně spusťte.

**Jak přidám podpora ladicího programu?**

Společnost Microsoft poskytuje podporu [běžné ladění protokolu](https://code.visualstudio.com/docs/extensionAPI/api-debugging) v budoucí verzi.

**Pokud VS podporované jazykové služby nainstalovaná (třeba JavaScriptu) již existuje, je možné i nadále nainstalovat rozšíření LSP jazyk serveru, která nabízí další funkce (například linting)?**

Ano, ale ne všechny funkce bude fungovat správně. Konečným cílem pro rozšíření serveru LSP jazyka je umožnit jazykových služeb nativně podporuje Visual Studio. Můžete vytvořit rozšíření, která nabízí další podporu LSP jazyk serverů, ale některé funkce (jako je například technologie IntelliSense) nebudou hladký. Obecně se doporučuje, LSP jazyk serveru rozšíření lze použít k poskytnutí nové prostředí pro jazyk, není rozšíření existující aplikace.

**Kde můžu publikovat Moje dokončené jazyk serveru LSP VSIX?**

Pokyny k Marketplace [tady](walkthrough-publishing-a-visual-studio-extension.md).

## <a name="see-also"></a>Viz také:

- [Přidání podpory editoru sady Visual Studio pro ostatní jazyky](../ide/adding-visual-studio-editor-support-for-other-languages.md)
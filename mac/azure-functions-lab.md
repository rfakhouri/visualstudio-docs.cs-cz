---
title: 'Kurz: Azure Functions'
description: Pomocí Azure functions v sadě Visual Studio for Mac.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 38FD2070-5151-482E-B0A9-993715128736
ms.openlocfilehash: 80c04182733204a18ee669d3851deab867cc56cd
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33877329"
---
# <a name="tutorial-getting-started-with-azure-functions"></a>Kurz: Začínáme s Azure Functions

V tomto testovacím prostředí získáte informace, jak začít pracovat, vytvoření funkce Azure pomocí sady Visual Studio for Mac. Budete také integrovat s tabulkami úložiště Azure, které představují jeden z mnoha druhy vazby a aktivační události, které jsou k dispozici pro vývojáře Azure Functions.

## <a name="objectives"></a>Cíle

> [!div class="checklist"]
> * Vytváření a ladění místní Azure Functions
> * Integraci se službou web a prostředky úložiště Azure
> * Orchestraci pracovního postupu zahrnující více Azure Functions

## <a name="requirements"></a>Požadavky

- Visual Studio pro Mac 7.5 nebo novější.
- Předplatné Azure (k dispozici bezplatná z [ https://azure.com/free ](https://azure.com/free)).

## <a name="exercise-1-creating-an-azure-functions-project"></a>Cvičení 1: Vytvoření projektu Azure Functions

1. Spusťte **Visual Studio pro Mac**.

1. Vyberte **soubor > Nový řešení**.

1. Z **cloudu > Obecné** kategorie, vyberte **Azure Functions** šablony. Použijete C# k vytvoření knihovny tříd rozhraní .NET, který je hostitelem Azure Functions. Klikněte na tlačítko **Další**.

    ![Výběr šablony Azure funkce](media/azure-functions-lab-image1.png)

1. Nastavte **název projektu** k **"AzureFunctionsLab"** a klikněte na tlačítko **vytvořit**.

    ![pojmenování a vytvoření projektu azure – funkce](media/azure-functions-lab-image2.png)

1. Rozbalte uzly v **řešení Pad**. Výchozí šablona projektu zahrnuje NuGet odkazy na celou řadu Azure WebJobs balíčky, stejně jako balíček Newtonsoft.Json. 

     Existují také tři soubory:- **host.json** popisujících globální konfiguraci možností konfigurace pro hostitele - **local.settings.json** pro konfiguraci nastavení služby. 
        -Šablona projektu vytvoří také výchozí HttpTrigger. Z důvodu toto testovací prostředí, měli byste odstranit **HttpTrigger.cs** souboru z projektu.

    Otevřete **local.settings.json**. Výchozí hodnota má dvě nastavení prázdný připojovací řetězec.

    ![soubor local.settings.json zobrazování pad řešení](media/azure-functions-lab-image3.png)

## <a name="exercise-2-creating-an-azure-storage-account"></a>Cvičení 2: Vytvoření účtu úložiště Azure

1. Přihlaste se k účtu Azure v [ https://portal.azure.com ](https://portal.azure.com).
 
1. V části **Oblíbené** části se nachází na levé straně obrazovky vyberte **účty úložiště**:

    ![Oblíbené položky části portálu Azure znázorňující položky účty úložiště](media/azure-functions-lab-image4.png)

1. Vyberte **přidat** k vytvoření nového účtu úložiště:

    ![Tlačítko Přidat nový účet úložiště](media/azure-functions-lab-image5.png)

1. Zadejte globálně jedinečného názvu pro **název** a použít ho znovu **skupiny prostředků**. Všechny ostatní položky můžete ponechat výchozí.

    ![nové podrobnosti účtu úložiště](media/azure-functions-lab-image6.png)

1. Klikněte na tlačítko **vytvořit**. Může trvat několik minut pro vytvoření účtu úložiště. Vám pošleme oznámení, jakmile byla úspěšně vytvořena.

    ![oznámení pro úspěšné nasazení](media/azure-functions-lab-image7.png)

1. Vyberte **přejděte k prostředku** tlačítko z oznámení.

1. Vyberte **přístupové klíče** kartě.

    ![nastavení klíče přístup](media/azure-functions-lab-image8.png)

1. Zkopírujte první **připojovací řetězec**. Tento řetězec se používá k integraci úložiště Azure s Azure Functions později.

    ![informace pro klíč 1](media/azure-functions-lab-image9.png)

1. Vraťte se do **Visual Studio pro Mac** a vložte úplný připojovací řetězec v jako **AzureWebJobsStorage** nastavení v **local.settings.json**. Nyní můžete odkazovat na název nastavení atributů pro funkce, které potřebují přístup k jeho prostředky.

    ![nastavení místního souboru s zadaný klíč připojení](media/azure-functions-lab-image10.png)

## <a name="example-3-creating-and-debugging-an-azure-function"></a>Příklad 3: Vytváření a ladění funkce Azure

1. Nyní jste připraveni začít přidávat nějaký kód. Při práci s knihovna tříd rozhraní .NET, Azure Functions se přidají jako statické metody. Z **řešení Pad**, klikněte pravým tlačítkem myši **AzureFunctions** uzel projektu a vyberte **Přidat > přidat funkci...** :

    ![Přidání funkcí – možnost](media/azure-functions-lab-image11.png)

1. V dialogovém okně Nový Azure Functions vyberte obecný webhook šablonu. Nastavte **název** k **přidat** a klikněte na tlačítko **Ok** k vytvoření funkce:

    ![Dialogové okno Nový řešení azure functions](media/azure-functions-lab-image12.png)

1. V horní části nový soubor, přidejte **pomocí** direktivy níže:

    ```csharp
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using System.Web;
    using Microsoft.WindowsAzure.Storage.Table;
    ```
1. Odeberte existující `Run` metoda a přidejte do třídy jako funkce Azure metodu níže:

    ```csharp
    [FunctionName("Add")]
    public static int Run(
    [HttpTrigger(AuthorizationLevel.Function, "get", Route = null)]
    HttpRequestMessage req,
    TraceWriter log)
    {
        int x = 1;
        int y = 2;

        return x + y;
    }
    ```
1. Projděme definici metody část podle část. 
    
    Je první věcí, které se zobrazí **%{FunctionName/** atribut, který se označuje jako funkce Azure tuto metodu. Atribut označí veřejný název funkce. Název atributu nemusí odpovídat názvu skutečné metoda.

    ![Nové spuštění metody s atributem %{FunctionName/ zvýrazněná](media/azure-functions-lab-image13.png)

1. Dále je označeno metodu **veřejné statické** metoda, která je vyžadována. Také můžete si všimnout, že návratová hodnota je **int**. Pokud není uvedeno jinak, pomocí atributů metoda, všechny není void návratová hodnota funkce Azure je vrácen do klienta jako text. Ve výchozím nastavení se vrátí jako **XML**, ale můžete změnit tak, aby **JSON**, které můžete to udělat později v testovacím prostředí.

    ![Nové spuštění metody se zvýrazněnou inicializace – metoda](media/azure-functions-lab-image14.png)

1. První parametr je označené jako **HttpTrigger** atribut, který označuje, že tato metoda je volána žádostí HTTP. Atribut také určuje úroveň autorizace metodu, jakož i pomocí příkazů podporuje (pouze **"GET"** v tomto případě). Může volitelně také můžete definovat **trasy** , přepíše cestu k metodu a nabízí způsob, jak automaticky extrahovat proměnné z cesty. Vzhledem k tomu **trasy** má hodnotu null, použije výchozí cestu k této metodě **/api/přidat**.

    ![Nové spuštění metody s parametrem zvýrazněná](media/azure-functions-lab-image15.png)

1. Poslední parametr metody **TraceWriter** který lze použít k protokolování zpráv pro diagnostiku a chyby.

    ![Nové spuštění metody se zvýrazněnou TraceWriter](media/azure-functions-lab-image16.png)

1. Nastavit zarážky **vrátit** řádek metody kliknutím u okraje řádku:

    ![Nastavte na návratový řádku zarážek](media/azure-functions-lab-image17.png)

1. Sestavit a spustit projekt v relaci ladění stisknutím **F5** nebo výběr **spustit > Spustit ladění**. Případně může klepnout **spustit** tlačítko. Všechny tyto možnosti provést stejný úkol. Odkazuje na zbytek této laboratoře **F5**, ale můžete použít metodu vás nejpohodlnější.

    ![Vytvoření a spuštění projektu](media/azure-functions-lab-image18.png)

1. Spuštění projektu se automaticky otevře aplikace terminálu.

1. Projekt projde proces zjišťování Azure Functions na základě atributy metody a názvů souborů, který je popsán později v tomto článku. V takovém případě zjistí jedné funkce Azure a "generuje" 1 pracovní funkci.

    ![Výstup Azure funkce v terminálu](media/azure-functions-lab-image19.png)

1. V dolní části zprávy spuštění vytiskne Azure Functions hostitele adresy URL všech triggeru protokolu HTTP rozhraní API. Musí existovat jenom jeden. Tuto adresu URL zkopírovat a vložit novou kartu prohlížeče.

    ![Adresa URL Azure funkce rozhraní API](media/azure-functions-lab-image20.png)

1. Zarážce by měly aktivovat okamžitě. Žádost o webové funkce směrování a nyní můžete ladit. Ukazatele myši **x** proměnné zobrazíte jeho hodnotu. 

    ![Aktivuje zarážek](media/azure-functions-lab-image21.png)

1. Odebrat zarážek stejným způsobem použít k přidání ho dříve (kliknutím na rozpětí nebo vyberte řádku a stiskněte klávesu **F9**).

1. Stiskněte klávesu **F5** dál běžet.

1. V prohlížeči bude vykreslen XML výsledek metody. Podle očekávání, operace přidání pevně zakódované vytvoří vyhovující součet. Všimněte si, pokud se zobrazí jenom tehdy "3" v prohlížeči Safari, přejděte k **Safari > Předvolby > Upřesnit** a osové "**zobrazit vyvíjet nabídky v řádku nabídek**" zaškrtávací políčko a načtením této stránky.

1. V **Visual Studio pro Mac**, klikněte **Zastavit** tlačítko Ukončit relaci ladění. Aby se zajistilo, že jsou zachyceny nové změny, nezapomeňte restartovat relaci ladění (Zastavit a znovu spusťte).

    ![Zastavte ladění možnost](media/azure-functions-lab-image22.png)

1. V **spustit** metoda, nahraďte **x** a **y** definice pomocí kódu níže. Tento kód extrahuje hodnoty z řetězce dotazu adresu URL, tak, že můžete provedeny operace přidání dynamicky podle parametrů.

    ```csharp
    var query = HttpUtility.ParseQueryString(req.RequestUri.Query);

    int x = int.Parse(query["x"]);

    int y = int.Parse(query["y"]);

    return x + y;
    ```
1. Spusťte aplikaci.

1. Vraťte se do okna prohlížeče a připojit řetězec `/?x=2&y=3` na adresu URL. Celá adresa URL by teď měly být `http://localhost:7071/api/Add?x=2&y=3`. Přejděte do nové adrese URL.

1. Tentokrát výsledkem by měla odpovídat nové parametry. Nebojte se, že spustit projekt s různými hodnotami. Všimněte si, že není k dispozici žádné kontroly chyb, bude vyvolána chyba, neplatné nebo chybějící parametry.

1. Ukončit relaci ladění.


## <a name="exercise-4-working-with-functionjson"></a>Cvičení 4: Práce s function.json

1.  V dřívějších cvičení jsme mluvili, že Visual Studio pro Mac "vygenerované" pracovní funkci funkce Azure, které jsou definovány v knihovně. Toto je, protože Azure Functions nepoužívá ve skutečnosti atributy metody za běhu, ale spíš používá vytváření systému kompilaci souboru konfigurace místa, a jak Azure Functions jsou k dispozici. Z **řešení Pad**, klikněte pravým tlačítkem na uzel projektu a vyberte **odhalit v hledání**.

     ![V nabídce vyhledávací odhalit](media/azure-functions-lab-image23.png)

1. Přejděte dolů na systém souborů, dokud se nedostanete **bin/Debug/netstandard2.0**. Měla by existovat složku s názvem **přidat**. Tato složka byla vytvořena tak, aby odpovídaly s názvem atributu funkce v kódu jazyka C#. Rozbalte složku přidat na nich jedné **function.json** souboru. Tento soubor se používá modulem runtime pro hostování a spravovat funkci Azure. Pro ostatní modely jazyk bez podpory kompilaci (například C# skript nebo JavaScript) tyto složky musí být ručně vytvářené a udržované. Pro C# vývojáře vygenerují automaticky z metadat atribut při sestavení. Klikněte pravým tlačítkem na **function.json** a vyberte ho otevřete v sadě Visual Studio.

    ![Function.JSON v adresáři souboru](media/azure-functions-lab-image24.png)

1. Zadané předchozích krocích tohoto kurzu, byste měli mít základní znalosti jazyka C# atributů. Která vezme v úvahu, tento formát JSON by měla vypadat povědomě. Existují však několik položek, které nejsou popsané v předchozích cvičení. Například každý **vazby** musí mít jeho **směr** nastavit. Jak vám může odvození, **"v"** znamená, že je vstupní parametr, zatímco **"se na"** označuje, že je parametr návratovou hodnotu (prostřednictvím **$return**) nebo **out** parametr metody. Budete taky muset zadat **Soubor_skriptu** (relativní vůči této konečného umístění) a **entryPoint** – metoda (veřejné a statické) v rámci sestavení. V dalším několik kroků přidáte vlastní funkce cesty pomocí tohoto modelu, zkopírujte obsah tohoto souboru do schránky.

    ![Function.JSON soubor otevřete v sadě visual studio pro mac](media/azure-functions-lab-image25.png)

1. V **řešení Pad**, klikněte pravým tlačítkem myši **AzureFunctionsLab** uzel projektu a vyberte **Přidat > novou složku**. Název nové složky **přidávání**. Podle konvence výchozí název této složky bude definuje cestu k rozhraní API, například **rozhraní api nebo přidávání**.

    ![Nová možnost složky](media/azure-functions-lab-image26.png)

1. Klikněte pravým tlačítkem myši **přidávání** složky a vyberte **Přidat > Nový soubor**.

    ![Nový soubor – možnost](media/azure-functions-lab-image27.png)

1. Vyberte **webové** kategorie a **prázdný soubor JSON** šablony. Nastavte **název** k **funkce** a klikněte na tlačítko **nový**.

    ![Možnost souboru prázdný json](media/azure-functions-lab-image28.png)

1. Umožňuje vložit obsah dalších **function.json** (z kroku 3) v nahraďte obsah výchozí nově vytvořený soubor.

1. Odeberte z horní části souboru json následující řádky:

    ```json
    "configurationSource":"attributes",
    "generatedBy":"Microsoft.NET.Sdk.Functions-1.0.13",
    ```

1. Na konci prvního vazby (po **"název": "req"** řádku), přidejte následující vlastnosti. Nezapomeňte zahrnout čárka na předchozí řádek. Tato vlastnost potlačuje výchozí kořen tak, že bude nyní extrahovat **int** parametry z cesty a umístěte je do parametry metody, které byly pojmenovány **x** a **y**.

    ```json
    "direction": "in",
    "route": "Adder/{x:int?}/{y:int?}"
    ```

1. Přidejte jiný vazby pod první. Tato vazba zpracuje návratovou hodnotu funkce. Nezapomeňte zahrnout čárka na předchozí řádek:

    ```json
    {
    "name": "$return",
    "type": "http",
    "direction": "out"
    }
    ```

1. Také aktualizovat **entryPoint** vlastnost v dolní části souboru použijte metodu s názvem **"Add2"**, tak jak je uvedeno níže. To je ilustrovat, cesta **rozhraní api nebo přidávání...**  může mapování na odpovídající metody s libovolným názvem (**Add2** sem).

    ```json
    "entryPoint": "<project-name>.<function-class-name>.Add2"
    ```

1. Váš koncový **function.json** soubor by měl vypadat jako následujícím kódu json:

    ```json
    {
    "bindings": [
        {
        "type": "httpTrigger",
        "methods": [
            "get"
        ],
        "authLevel": "function",
        "direction": "in",
        "name": "req",
        "route": "Adder/{x:int?}/{y:int?}"
        },
        {
        "name": "$return",
        "type": "http",
        "direction": "out"
        }
    ],
    "disabled": false,
    "scriptFile": "../bin/AzureFunctionsProject.dll",
    "entryPoint": "AzureFunctionsProject.Add.Add2"
    }
    ```

1. Jeden poslední krok potřeba udělat všechny pracovní je dáte pokyn, aby Visual Studio pro Mac zkopírujte tento soubor do stejné relativní cestu do výstupního adresáře pokaždé, když se změní. Se vybraný soubor, vyberte na kartě vlastnosti z pravém panelu a pro **kopírovat do výstupního adresáře** vyberte **kopírovat, pokud je novější**:

    ![Vlastnosti možnosti souboru json](media/azure-functions-lab-image30.png)

1. V **Add.cs**, nahraďte `Run` – metoda (včetně atribut) pomocí následující metody ke splnění očekávané funkce. Je velmi podobné `Run`kromě toho, že používá žádné atributy a má explicitní parametry pro **x** a **y**.

    ```csharp
    public static int Add2(
        HttpRequestMessage req,
        int x,
        int y,
        TraceWriter log)
    {
        return x + y;
    }
    ```
1. Stiskněte klávesu **F5** sestavení a spuštění projektu.

1. Sestavení se dokončí a platformy otáčí nahoru, teď bude indikovat, že je k dispozici pro požadavky, které se mapuje na nově přidané metoda druhý trasy:

    ![Adresa URL pro funkce protokolu Http](media/azure-functions-lab-image31.png)

1. Vrátí okno prohlížeče a přejděte do **http://localhost:7071/api/Adder/3/5**.

1. Znovu, tentokrát metoda funguje, stahování parametry z cesty a vytváření součet.

1. Vraťte se do **Visual Studio pro Mac** a ukončení relace ladění.

## <a name="exercise-5-working-with-azure-storage-tables"></a>Cvičení 5: Práce s tabulkami úložiště Azure

Službu, kterou vytvoříte často, může být mnohem složitější než co jsme, pokud jste vytvořili a vyžadovat značné množství času nebo infrastrukturu k provádění. V tomto případě může pro vás efektivní tak, aby přijímal požadavky, které jsou zařazeny do fronty pro zpracování, je-li k dispozici prostředky, které Azure Functions poskytuje podporu pro. V ostatních případech budete chtít ukládat data centrálně. Tabulky Azure Storage umožňují rychle udělat. 

1. Přidání třídy níže na **Add.cs**. Má přejít do oboru názvů, ale mimo existující třídy.

    ```csharp
    public class TableRow : TableEntity
    {
        public int X { get; set; }
        public int Y { get; set; }
        public int Sum { get; set; }
    }
    ```
1. V rámci **přidat** třídy, přidejte kód níže zavést jinou funkci. Všimněte si, že tato jedinečná, pokud v tom, že ji nebude zahrnovat odpovědi HTTP. Vrátí poslední řádek novou **řádků tabulky** naplněný některé klíčové informace, které se snadno načíst později na (**PartitionKey** a **RowKey**), jakož i jeho parametry a součet. Kód v metodě také používá **TraceWriter** usnadnění vědět, když je funkce spuštěná.

    ```csharp
    [FunctionName("Process")]
    [return: Table("Results")]
    public static TableRow Process(
        [HttpTrigger(AuthorizationLevel.Function, "get",
            Route = "Process/{x:int}/{y:int}")]
        HttpRequestMessage req,
        int x,
        int y,
        TraceWriter log)
    {
        log.Info($"Processing {x} + {y}");
    
        return new TableRow()
        {
            PartitionKey = "sums",
            RowKey = $"{x}_{y}",
            X = x,
            Y = y,
            Sum = x + y
        };
    }
    ```
1. Stiskněte klávesu **F5** sestavení a spuštění projektu.

1. Na záložce prohlížeče přejděte na **http://localhost:7071/api/Process/4/6**. Tím bude přidán další zprávu do fronty, který by měla vést nakonec v jiném řádku, který chcete přidat do tabulky.

1. Vraťte se do **Terminálové** a sledujte pro příchozí žádost o **4 + 6**.

    ![Žádost o přidání zobrazující terminálu výstup](media/azure-functions-lab-image32.png)

1. Vraťte se do prohlížeče, aktualizujte požadavek na stejnou adresu URL. Tentokrát uvidíte chybu **proces** metoda. Je to proto, že kód se pokouší přidat řádek do tabulky Azure Table Storage pomocí oddílu a řádku kombinace klíče, který již existuje.

    ``` 
    System.Private.CoreLib: Exception while executing function: Process. Microsoft.Azure.WebJobs.Host: Error while handling parameter $return after function returned:. Microsoft.Azure.WebJobs.Host: The specified entity already exists.
    ```

1. Ukončete relaci ladění.

1. Pro zmírnění chyby, přidejte následující parametr k definici metoda bezprostředně před **TraceWriter** parametr. Tento parametr nastaví platformou Azure Functions k pokusu o načtení **řádků tabulky** z **výsledky** tabulky na **PartitionKey** jsme už používá k uložení výsledky. Ale některé skutečné magic dodává do play Pokud zjistíte, že **RowKey** je generován dynamicky podle dalších **x** a **y** parametry pro velmi stejné Metoda. Pokud tento řádek již existuje, pak **řádků tabulky** bude mít ji, když metoda začíná žádné další práci vyžadovanou vývojář. Pokud řádek neexistuje, pak budete mít pouze hodnotu null. Tento druh efektivitu umožňuje vývojářům soustředit na důležité obchodní logiky a není infrastruktury.

    ```csharp
    [Table("Results", "sums", "{x}_{y}")]
    TableRow tableRow,
    ```
1. Přidejte na začátek metody kód níže. Pokud **řádků tabulky** není null, pak jsme už máte výsledky pro požadovanou operaci a může vrátit okamžitě. Funkce, jinak hodnota pokračuje jako předtím. Toto nemusí být nejvíce robustní způsob, jak můžete vrátit data, znázorňuje bodu, můžete orchestraci mimořádně sofistikované operace napříč více škálovatelné vrstev s velmi malé kódem.

    ```csharp
    if (tableRow != null)
    {
        log.Info($"{x} + {y} already exists");
        return null;
    }
    ```
1. Stiskněte klávesu **F5** sestavení a spuštění projektu.

1. Na záložce prohlížeče aktualizujte adresu URL v **http://localhost:7071/api/Process/4/6**. Vzhledem k tomu, že řádku tabulky pro tento záznam existuje, měla by vrátit okamžitě a bez chyby. Vzhledem k tomu, že neexistuje žádný výstup protokolu HTTP, zobrazí se výstup v terminálu.

    ![Terminálu výstup zobrazující řádku tabulky již existuje](media/azure-functions-lab-image33.png)

1. Aktualizace adresu URL, aby odrážela kombinaci není ještě testovány, jako například **http://localhost:7071/api/Process/5/7**. Všimněte si zprávy v terminálu, který označuje, že řádku tabulky nebyl nalezen (podle očekávání).

    ![Nový proces zobrazující terminálu výstup](media/azure-functions-lab-image34.png)

1. Vraťte se do **Visual Studio pro Mac** a ukončení relace ladění.

<!--
1. Finally, let's take a look at what it's like to work with multiple input records. Rather than specify a specific **TableRow**, you can request an **IQueryable<TableRow>** using the same attributes, and the runtime will fill it with the appropriate resource you need. Add the code below to create a **List** function that lists all items that currently exist in the Azure table we've been working with. Also note that we're specifying that the MIME type of the response is **application/json**, so the runtime will automatically render as JSON. 

    ```csharp
    [FunctionName("List")]
    public static HttpResponseMessage List(
        [HttpTrigger(AuthorizationLevel.Function, "get", Route = null)]
        HttpRequestMessage req,
        [Table("Results", "sums")]
        IQueryable<TableRow> table,
        TraceWriter log)
    {
        return req.CreateResponse(HttpStatusCode.OK, table, "application/json");
    }
    ```
1. Press **F5** to build and run the project.

1. In the browser tab, navigate to **http://localhost:7071/api/List**. This should pull down the list of all items in the Azure table and render it as JSON.

    ![](https://user-images.githubusercontent.com/3944468/29033725-be9d5a5e-7b4a-11e7-8b55-df0a200b6320.png)
-->

## <a name="summary"></a>Souhrn

V tomto testovacím prostředí když jste se naučili jak začít pracovat, vytvoření funkce Azure pomocí sady Visual Studio for Mac.


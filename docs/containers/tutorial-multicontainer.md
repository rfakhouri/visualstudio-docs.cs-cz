---
title: Visual Studio kontejnerových nástrojů vícekontejnerových kurz pomocí Docker Compose a ASP.NET Core
author: ghogen
description: Další informace o použití více kontejnerů pomocí Docker Compose
ms.author: ghogen
ms.date: 02/21/2019
ms.technology: vs-azure
ms.topic: include
ms.openlocfilehash: 28b9cf02c29f488f50499e4ef52eacf18184981d
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59652284"
---
# <a name="tutorial-create-a-multi-container-app-with-docker-compose"></a>Kurz: Vytvoření vícekontejnerové aplikace pomocí Docker Compose

V tomto kurzu se dozvíte, jak spravovat více než jednoho kontejneru a komunikaci mezi nimi při použití nástroje pro kontejnery v sadě Visual Studio.  Správa několika kontejnerů vyžaduje *Orchestrace kontejnerů* a vyžaduje orchestrátor Docker Compose, Kubernetes nebo Service Fabric. Zde použijeme, Docker Compose. Docker Compose se skvěle hodí pro místní ladění a testování v průběhu vývojového cyklu.

## <a name="prerequisites"></a>Požadavky

::: moniker range="vs-2017"
* [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
* [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) s **vývoj pro Web**, **nástroje Azure** úlohy, nebo **vývoj pro různé platformy .NET Core** nainstalovaná úloha
::: moniker-end

::: moniker range=">= vs-2019"
* [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) s **vývoj pro Web**, **nástroje Azure** úlohy, a/nebo **vývoj pro různé platformy .NET Core** nainstalovaná úloha
* [Aktualizace 2.2 vývojové nástroje .NET core](https://dotnet.microsoft.com/download/dotnet-core/2.2) pro vývoj aplikací pomocí .NET Core 2.2
::: moniker-end

## <a name="create-a-web-application-project"></a>Vytvoření projektu webové aplikace

V sadě Visual Studio, vytvořit **webové aplikace ASP.NET Core** projekt s názvem `WebFrontEnd`. Vyberte **webovou aplikaci** a vytvořte webovou aplikaci se stránkami Razor. 
  
::: moniker range="vs-2017"

Nesmí být zvolen **povolit podporu Dockeru**. Dále přidáte podporu Dockeru.

![Snímek obrazovky vytvoření webového projektu](./media/tutorial-multicontainer/docker-tutorial-enable-docker-support.png)

::: moniker-end

::: moniker range="vs-2019"

![Snímek obrazovky vytvoření webového projektu](./media/tutorial-multicontainer/vs-2019/new-aspnet-core-project1.png)

Nesmí být zvolen **povolit podporu Dockeru**. Dále přidáte podporu Dockeru.

![Snímek obrazovky vytvoření webového projektu](./media/tutorial-multicontainer/vs-2019/new-aspnet-core-project.png)

::: moniker-end

## <a name="create-a-web-api-project"></a>Vytvořte projekt webového rozhraní API

Přidat projekt do stejného řešení a jeho volání *MyWebAPI*. Vyberte **API** jako projekt typu a zrušte zaškrtnutí políčka pro **konfigurace pro protokol HTTPS**. V tomto návrhu používáme jenom protokol SSL pro komunikaci s klientem, nikoli pro komunikaci mezi kontejnery v stejnou webovou aplikaci. Pouze `WebFrontEnd` vyžaduje protokol HTTPS.

::: moniker range="vs-2017"
   ![Snímek obrazovky vytváření projektu webového rozhraní API](./media/tutorial-multicontainer/docker-tutorial-mywebapi.png)
::: moniker-end
::: moniker range="vs-2019"
   ![Snímek obrazovky vytváření projektu webového rozhraní API](./media/tutorial-multicontainer/vs-2019/web-api-project.png)
::: moniker-end

## <a name="add-code-to-call-the-web-api"></a>Přidejte kód pro volání webového rozhraní API

1. V `WebFrontEnd` projekt, otevřete *Index.cshtml.cs* soubor a nahradit `OnGet` metodu s následujícím kódem.

   ```csharp
    public async Task OnGet()
    {
       ViewData["Message"] = "Hello from webfrontend";

       using (var client = new System.Net.Http.HttpClient())
       {
          // Call *mywebapi*, and display its response in the page
          var request = new System.Net.Http.HttpRequestMessage();
          request.RequestUri = new Uri("http://mywebapi/api/values/1");
          var response = await client.SendAsync(request);
          ViewData["Message"] += " and " + await response.Content.ReadAsStringAsync();
       }
    }
   ```

1. V *Index.cshtml* přidejte řádek pro zobrazení `ViewData["Message"]` tak, že soubor bude vypadat jako v následujícím kódu:
    
      ```cshtml
      @page
      @model IndexModel
      @{
          ViewData["Title"] = "Home page";
      }
    
      <div class="text-center">
          <h1 class="display-4">Welcome</h1>
          <p>Learn about <a href="https://docs.microsoft.com/aspnet/core">building Web apps with ASP.NET Core</a>.</p>
          <p>@ViewData["Message"]</p>
      </div>
      ```

1. Teď v projektu webového rozhraní API, přidejte kód do kontroleru hodnoty chcete přizpůsobit zprávu o vrácená rozhraním API pro volání, které jste přidali z *webfrontend*.
    
      ```csharp
        // GET api/values/5
        [HttpGet("{id}")]
        public ActionResult<string> Get(int id)
        {
            return "webapi (with value " + id + ")";
        }
      ```

1. V `WebFrontEnd` projektu, zvolte **Přidat > Podpora Orchestrátoru kontejnerů**. **Možnosti podpory Dockeru** se zobrazí dialogové okno.

1. Zvolte **Docker Compose**.

1. Zvolte váš cílový operační systém, například Linux.

   ![Snímek obrazovky s výběrem cílový operační systém](media/tutorial-multicontainer/docker-tutorial-docker-support-options.PNG)

   Visual Studio vytvoří *docker-compose.yml* souboru a *.dockerignore* soubor **docker-compose** uzel v řešení a daný projekt zobrazuje textu psaného tučným písmem předvede vám, že se jedná o projekt po spuštění.

   ![Snímek obrazovky Průzkumníka řešení docker-compose projektu přidán](media/tutorial-multicontainer/multicontainer-solution-explorer.png)

   *Docker-compose.yml* se zobrazí takto:

   ```yaml
   version: '3.4'

    services:
      webfrontend:
        image: ${DOCKER_REGISTRY-}webfrontend
        build:
          context: .
          dockerfile: WebFrontEnd/Dockerfile
   ```

   *.Dockerignore* soubor obsahuje typy souborů a přípony, které nechcete zahrnout v kontejneru Dockeru. Tyto soubory jsou obecně přidružené prostředí pro vývoj a Správa zdrojového kódu, není součástí aplikace nebo služby, kterou vyvíjíte.

   Podívejte se na **kontejnerových nástrojů** části podokna výstup podrobnosti příkazy spuštěn.  Zobrazí se nástroj příkazového řádku docker-compose slouží k nakonfigurování a vytvoření kontejnerů modulu runtime.

1. V projektu webového rozhraní API, znovu klikněte pravým tlačítkem na uzel projektu a zvolte **přidat** > **podporu Orchestrátoru kontejnerů**. Zvolte **Docker Compose**a pak vyberte stejný cílový operační systém.  

    > [!NOTE]
    > V tomto kroku nabídne Visual Studio k vytvoření souboru Dockerfile. Pokud to uděláte na projekt, který už má podporu Dockeru, zobrazí se výzva, jestli chcete přepsat existující soubor Dockerfile. Pokud jste provedli změny ve vašem souboru Dockerfile, který budete chtít zachovat, zvolte možnost Ne.

    Visual Studio se provede několik změn vaše docker compose YML souboru. Obě služby jsou teď součástí.

    ```yaml
    version: '3.4'
    
    services:
      webfrontend:
        image: ${DOCKER_REGISTRY-}webfrontend
        build:
          context: .
          dockerfile: WebFrontEnd/Dockerfile
    
      mywebapi:
        image: ${DOCKER_REGISTRY-}mywebapi
        build:
          context: .
          dockerfile: MyWebAPI/Dockerfile
    ```

1. Spuštění tohoto webu místně teď (F5 nebo Ctrl + F5) ověřte, že funguje dle očekávání. Pokud je vše nastaveno správně, zobrazí se zpráva "Hello z webfrontend a webová rozhraní API (s hodnotou 1)."

   Který se spustí při spuštění nebo ladění nastaven první projekt, který používáte při přidání Orchestrace kontejnerů. Můžete nakonfigurovat v akci spuštění **vlastnosti projektu** docker-compose projektu.  Na uzel projektu docker-compose, klikněte pravým tlačítkem na otevřete kontextovou nabídku a zvolte **vlastnosti**, nebo použijte kombinaci kláves Alt + Enter.  Následující snímek obrazovky ukazuje vlastnosti, které je vhodné pro řešení se tady použít.  Například můžete změnit na stránce, která jsou načtená přizpůsobením **adresa URL služby** vlastnost.

   ![Snímek obrazovky vlastností projektu docker-compose](media/tutorial-multicontainer/launch-action.png)

   Tady se zobrazí při spuštění:

   ![Snímek obrazovky s funkční webovou aplikaci](media/tutorial-multicontainer/webfrontend.png)

## <a name="next-steps"></a>Další kroky

Podívejte se na možnosti nasazení vaší [kontejnerů Azure](/azure/containers).

## <a name="see-also"></a>Viz také:
  
[Docker Compose](https://docs.docker.com/compose/)  
[Nástroje pro kontejnery](/visualstudio/containers/)

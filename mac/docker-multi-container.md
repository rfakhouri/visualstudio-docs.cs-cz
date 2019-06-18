---
title: Kurz – vytvoření více kontejnerů aplikace pomocí Docker Compose
description: Zjistěte, jak spravovat více než jednoho kontejneru a komunikaci mezi nimi v sadě Visual Studio pro Mac
author: bytesguy
ms.author: adhartle
ms.date: 06/17/2019
ms.openlocfilehash: df130e86de7f35c43459a70a12c0e9cfafbbe3a4
ms.sourcegitcommit: fd5a5b057df3d733f5224c305096907989811f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/18/2019
ms.locfileid: "67196405"
---
# <a name="create-a-multi-container-app-with-docker-compose"></a>Vytvoření více kontejnerů aplikace pomocí Docker Compose

V tomto kurzu se naučíte spravovat více než jednoho kontejneru a komunikaci mezi nimi používáte Docker Compose v sadě Visual Studio pro Mac.

## <a name="prerequisites"></a>Požadavky

* [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-mac)
* [Visual Studio for Mac 2019](https://visualstudio.microsoft.com/vs/mac)

## <a name="create-an-aspnet-core-web-application-and-add-docker-support"></a>Vytvořit webovou aplikaci ASP.NET Core a přidání podpory Dockeru

1. Vytvořit nové řešení tak, že přejdete do **soubor > Nový řešení**.
1. V části **.NET Core > aplikace** zvolte **webovou aplikaci** šablony: ![Vytvoření nové aplikace ASP.NET](media/docker-quickstart-1.png)
1. Vyberte cílovou architekturu. V tomto příkladu budeme používat .NET Core 2.2: ![Nastavení cílové architektury](media/docker-quickstart-2.png)
1. Zadejte podrobnosti o projektu, jako je například název projektu (_DockerDemoFrontEnd_ v tomto příkladu) a název řešení (_DockerDemo_). Vytvořený projekt obsahuje všechny základní informace, které potřebujete k sestavení a spuštění webu technologie ASP.NET Core.
1. V oblasti řešení klikněte pravým tlačítkem na projekt DockerDemoFrontEnd a vyberte **Add > Add Docker Support**: ![Přidání podpory dockeru](media/docker-quickstart-3.png)

Visual Studio pro Mac automaticky přidá nový projekt do řešení volá **docker-compose** a přidejte **soubor Dockerfile** do existujícího projektu.

## <a name="create-an-aspnet-core-web-api-and-add-docker-support"></a>Vytvoření webového rozhraní API ASP.NET Core a přidání podpory Dockeru

Dále vytvoříme druhý projekt, který bude sloužit jako naše back-endového rozhraní API. **Rozhraní API pro .NET Core** šablona obsahuje kontroler, který umožňuje zpracovávat požadavky RESTful.

1. Přidat nový projekt do stávajícího řešení tak, že kliknete pravým tlačítkem na řešení a zvolíte **Přidat > Přidat nový projekt**.
1. V části **.NET Core > aplikace** zvolte **API** šablony.
1. Vyberte cílovou architekturu. V tomto příkladu budeme používat .NET Core 2.2
1. Zadejte podrobnosti o projektu, jako je například název projektu (_DockerDemoAPI_ v tomto příkladu).
1. Po vytvoření, přejděte na oblasti řešení a projektu DockerDemoAPI klikněte pravým tlačítkem myši a vyberte **Add > Add Docker Support**.

**Docker-compose.yml** soubor **docker-compose** projekt se automaticky aktualizují zahrnout projekt rozhraní API spolu s existující projekt webové aplikace. Když jsme sestavit a spustit **docker-compose** projektu, každý z těchto projektů se nasadí do samostatného kontejneru Dockeru.

```
version: '3.4'

services:
  dockerdemofrontend:
    image: ${DOCKER_REGISTRY-}dockerdemofrontend
    build:
      context: .
      dockerfile: DockerDemoFrontEnd/Dockerfile

  dockerdemoapi:
    image: ${DOCKER_REGISTRY-}dockerdemoapi
    build:
      context: .
      dockerfile: DockerDemoAPI/Dockerfile
```

## <a name="integrate-the-two-containers"></a>Integrace dvou kontejnerů

Teď máme dva projekty ASP.NET v našich řešení a jsou nakonfigurovány s podporou Dockeru. Dále je potřeba přidat nějaký kód!

1. V `DockerDemoFrontEnd` projekt, otevřete *Index.cshtml.cs* soubor a nahradit `OnGet` metodu s následujícím kódem:

   ```csharp
    public async Task OnGet()
    {
       ViewData["Message"] = "Hello from webfrontend";

       using (var client = new System.Net.Http.HttpClient())
       {
          // Call *mywebapi*, and display its response in the page
          var request = new System.Net.Http.HttpRequestMessage();
          request.RequestUri = new Uri("http://dockerdemoapi/api/values/1");
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

1. Teď v projektu webového rozhraní API, přidejte kód do kontroleru hodnoty chcete přizpůsobit zprávu o vrácená rozhraním API pro volání, které jste přidali z *webfrontend*:
    
      ```csharp
        // GET api/values/5
        [HttpGet("{id}")]
        public ActionResult<string> Get(int id)
        {
            return "webapi (with value " + id + ")";
        }
      ```
1. Nastavte `docker-compose` projekt jako spouštěný projekt, přejděte na **spuštění > Spustit ladění**. Pokud je vše nastaveno správně, zobrazí zprávu "Hello z webfrontend a webová rozhraní API (s hodnotou 1).":

![Řešení kontejnerů dockeru s více spuštění](media/docker-multicontainer-debug.png)

---
title: Vytvoření prostředí pro vývoj .NET Core s kontejnery pomocí Kubernetes v cloudu pomocí sady Visual Studio – krok 5 – volání jiného kontejneru | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: ab3934e6f7f013dd21309dc8c98461983bdfe30a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31898424"
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Začínáme v připojeném prostředí s .NET Core a Visual Studio

Předchozí krok: [ladění kontejner v Kubernetes](get-started-netcore-visualstudio-04.md)

## <a name="call-another-container"></a>Volání jiného kontejneru
V této části vytvoříme vytvoření druhého služby `mywebapi`a mít `webfrontend` volání. Každá služba se spustí v oddělené kontejnery. Jsme budete ladění napříč obou kontejnery.

![](media/multi-container.png)

## <a name="download-sample-code-for-mywebapi"></a>Stáhněte si ukázkový kód pro *mywebapi*
Z důvodu čas umožňuje stáhnout ukázkový kód z úložiště Githubu. Přejděte na https://github.com/Azure/vsce a vyberte **klonovat nebo stáhnout** ke stažení úložiště GitHub. Kód pro tento oddíl je v `vsce/samples/dotnetcore/getting-started/mywebapi`.

## <a name="run-mywebapi"></a>Run *mywebapi*
1. Otevřete projekt `mywebapi` v *samostatném okně Visual Studio*.
1. Vyberte **připojené prostředí pro AKS** z rozevíracího seznamu nastavení spuštění jako jste provedli dříve `webfrontend` projektu. Spíše než tato doba pro vytvoření nové vývojové prostředí, vyberte stejný jako ten, jste již vytvořili. Stejně jako před ponechejte uvedena do výchozího stavu místo `mainline` a klikněte na tlačítko **OK**. V okně výstupu může dojít k sadě Visual Studio spustí "tedy" Tato nová služba ve vašem vývojovém prostředí k urychlení věcí až při spuštění ladění,
1. Stiskněte F5 a počkejte, služby pro vytváření a nasazení. Budete vědět, že je připraven při stavového řádku sadě Visual Studio změní oranžová
1. Poznamenejte si koncový bod adresy URL se zobrazí v **připojené prostředí pro AKS** v podokně **výstup** okně ho bude vypadat podobně jako http://localhost: \<ČísloPortu\>. To nemusí připadat jako kontejner běží místně, ale ve skutečnosti je spuštěna v našem vývojového prostředí v Azure.
1. Když `mywebapi` je připravené, otevřete prohlížeč na adresu místního hostitele a připojit `/api/values` na adresu URL pro vyvolání výchozí GET rozhraní API služby `ValuesController`. 
1. Pokud všechny kroky byly úspěšné, byste měli vidět odpovědi z `mywebapi` služba, která vypadá takto.

    ![](images/WebAPIResponse.png)

## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>Vytvoření žádosti o z *webfrontend* k *mywebapi*
Můžete teď napsat kód `webfrontend` , vytváří požadavek na `mywebapi`. Přejít do okna Visual Studio, který má `webfrontend` projektu. V `HomeController.cs` soubor *nahradit* kód pro metodu o následujícím kódem:

 ```csharp
    public async Task<IActionResult> About()
    {
        ViewData["Message"] = "Hello from webfrontend";
        
        // Use HeaderPropagatingHttpClient instead of HttpClient so we can propagate
        // headers in the incoming request to any outgoing requests
        using (var client = new HeaderPropagatingHttpClient(this.Request))
        {
            // Call *mywebapi*, and display its response in the page
            var response = await client.GetAsync("http://mywebapi/api/values/1");
            ViewData["Message"] += " and " + await response.Content.ReadAsStringAsync();
        }
    
        return View();
    }

```

Všimněte si, jak je zjišťování služby DNS Kubernetes' vzhledem k odkazování na služby jako `http://mywebapi`. **Kód v našem vývojového prostředí běží stejným způsobem, který se spustí v produkčním prostředí**.

V předchozím příkladu kódu také využívá `HeaderPropagatingHttpClient` třídy. Tato pomocná třída je soubor `HeaderPropagation.cs` který byl přidán do projektu, když jste nakonfigurovali na používání prostředí připojen. `HeaderPropagatingHttpClient` je odvozený od dobře známé `HttpClient` třídy a přidá funkce potřebný k šíření konkrétní hlavičky z existujícího objektu ASP .NET požadavku HTTP do odchozí objektu HttpRequestMessage. Ukážeme, jak později to usnadňuje produktivitu vývojového prostředí v rámci scénáře team.

## <a name="debug-across-multiple-services"></a>Ladění ve více službách
1. V tomto okamžiku `mywebapi` by měla být stále spuštěná pomocí ladicího programu připojen. Pokud není, stiskněte F5 v `mywebapi` projektu.
1. Nastavte zarážky v `Get(int id)` metoda v `ValuesController.cs` soubor, který zpracovává `api/values/{id}` požadavky GET.
1. V `webfrontend` projektu, kde jsme vložit ve výše uvedeném kódu nastavit zarážky těsně před odešle požadavek GET na `mywebapi/api/values`.
1. Stiskněte F5 v `webfrontend` projektu. Visual Studio znovu otevřete prohlížeč na příslušné localhost port a webové aplikace se zobrazí.
1. Klikněte na "**o**" odkaz v horní části stránky pro aktivaci zarážka v `webfrontend` projektu. 
1. Stiskněte tlačítko F10 pokračovat. Zarážka v `mywebapi` projektu se teď spustí.
1. Přístupů F5, aby bylo možné pokračovat a bude zpět v kódu v `webfrontend` projektu.
1. Stále mačkat F5, ještě jednou dokončit žádost a vrátit na stránku v prohlížeči. Ve webové aplikaci, o stránky se zobrazí zpráva zřetězených dvě služby: "Hello z webfrontend a Hello z mywebapi".

Skvělá práce! Nyní máte aplikace s více kontejnerů, kde může každý kontejner vyvinuté a nasazuje samostatně.

> [!div class="nextstepaction"]
> [Další informace o vývoj v týmu](get-started-netcore-visualstudio-06.md)


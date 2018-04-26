---
title: Vytvoření prostředí pro vývoj .NET Core s kontejnery pomocí Kubernetes v cloudu – krok 5 – volání jiný kontejner | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 6ef3a79d0b79feae64adcaebe31daa48ba75ab75
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>Začínáme v připojeném prostředí s .NET Core

Předchozí krok: [ladění kontejner v Kubernetes](get-started-netcore-04.md)

V této části vytvoříme vytvoření druhého služby `mywebapi`a mít `webfrontend` volání. Každá služba se spustí v oddělené kontejnery. Jsme budete ladění napříč obou kontejnery.

![](media/multi-container.png)

## <a name="download-sample-code-for-mywebapi"></a>Stáhněte si ukázkový kód pro *mywebapi*
Z důvodu čas umožňuje stáhnout ukázkový kód z úložiště Githubu. Přejděte na https://github.com/Azure/vsce a vyberte **klonovat nebo stáhnout** ke stažení úložiště GitHub. Kód pro tento oddíl je v `vsce/samples/dotnetcore/getting-started/mywebapi`.


## <a name="run-mywebapi"></a>Run *mywebapi*
1. Otevřete složku `mywebapi` v *samostatném okně VS Code*.
1. Stiskněte F5 a počkejte, služby pro vytváření a nasazení. Budete vědět, že je připraven, jakmile se zobrazí na panelu ladění VS Code.
1. Všimněte si adresy URL koncového bodu, bude stránka vypadat nějak podobně jako http://localhost: \<ČísloPortu\>. **Tip: Zobrazí stavový řádek VS Code prokliknutelný adresy URL.** To nemusí připadat jako kontejner běží místně, ale ve skutečnosti je spuštěna v našem vývojového prostředí v Azure. Je z důvodu pro adresu místního hostitele, protože `mywebapi` nebylo definováno žádné veřejné koncové body a můžete přistupovat pouze z v rámci Kubernetes instance. Pro usnadnění vaší práce a usnadňuje interakci s privátní služby z místního počítače připojení prostředí vytvoří dočasný tunelového propojení SSH ke kontejneru, který běží v Azure.
1. Když `mywebapi` připravené, otevřete prohlížeč na adresu místního hostitele. Připojit `/api/values` na adresu URL pro vyvolání výchozí GET rozhraní API služby `ValuesController`. 
1. Pokud všechny kroky byly úspěšné, byste měli vidět odpovědi z `mywebapi` služby.


## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>Vytvoření žádosti o z *webfrontend* k *mywebapi*
Můžete teď napsat kód `webfrontend` , vytváří požadavek na `mywebapi`.
1. Přejít do okna VS Code pro `webfrontend`.
1. *Nahraďte* kód pro metodu o:

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

V předchozím příkladu kódu také využívá `HeaderPropagatingHttpClient` třídy. Tato pomocná třída byl přidán do složky kódu v době jste spustili `vsce init`. `HeaderPropagatingHttpClient` je dervied z dobře známé `HttpClient` třídy a přidá funkce potřebný k šíření konkrétní hlavičky z existujícího objektu ASP .NET požadavku HTTP do odchozí objektu HttpRequestMessage. Ukážeme, jak později to usnadňuje produktivitu vývojového prostředí v rámci scénáře team.


## <a name="debug-across-multiple-services"></a>Ladění ve více službách
1. V tomto okamžiku `mywebapi` by měla být stále spuštěná pomocí ladicího programu připojen. Pokud není, stiskněte F5 v `mywebapi` projektu.
1. Nastavte zarážky v `Get(int id)` metoda, která zpracovává `api/values/{id}` požadavky GET.
1. V `webfrontend` projektu, zarážku těsně před odešle požadavek GET na `mywebapi/api/values`.
1. Stiskněte F5 v `webfrontend` projektu.
1. Vyvolání webové aplikace a krok prostřednictvím kódu v obou služeb.
1. Ve webové aplikaci, o stránky se zobrazí zpráva zřetězených dvě služby: "Hello z webfrontend a Hello z mywebapi".


Skvělá práce! Nyní máte aplikace s více kontejnerů, kde může každý kontejner vyvinuté a nasazuje samostatně.

> [!div class="nextstepaction"]
> [Další informace o vývoj v týmu](get-started-netcore-06.md)


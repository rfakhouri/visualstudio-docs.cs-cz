---
title: Vytvoření prostředí pro vývoj Node.js s kontejnery pomocí Kubernetes v cloudu – krok 5 – volání jiný kontejner | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 89565869feec746aff75327b59ee7d0b466f26c1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Začínáme v připojeném prostředí s Node.js

Předchozí krok: [ladění kontejner v Kubernetes](get-started-nodejs-04.md)

V této části vytvoříme vytvoření druhého služby `mywebapi`a mít `webfrontend` volání. Každá služba se spustí v oddělené kontejnery. Jsme budete ladění napříč obou kontejnery.

![](media/multi-container.png)

## <a name="open-sample-code-for-mywebapi"></a>Otevřete ukázkový kód pro *mywebapi*
Byste již měli mít ukázkový kód pro `mywebapi` této příručce v části složku s názvem `vsce/samples` (Pokud ne, přejděte na https://github.com/Azure/vsce a vyberte **klonovat nebo stáhnout** ke stažení úložiště GitHub.) Kód pro tento oddíl je v `vsce/samples/nodejs/getting-started/mywebapi`.

## <a name="run-mywebapi"></a>Run *mywebapi*
1. Otevřete složku `mywebapi` v *samostatném okně VS Code*.
1. Stiskněte F5 a počkejte, služby pro vytváření a nasazení. Budete vědět, že je připraven, jakmile se zobrazí na panelu ladění VS Code.
1. Všimněte si adresy URL koncového bodu, bude stránka vypadat nějak podobně jako http://localhost: \<ČísloPortu\>. **Tip: Zobrazí stavový řádek VS Code prokliknutelný adresy URL.** To nemusí připadat jako kontejner běží místně, ale ve skutečnosti je spuštěna v našem vývojového prostředí v Azure. Je z důvodu pro adresu místního hostitele, protože `mywebapi` nebylo definováno žádné veřejné koncové body a můžete přistupovat pouze z v rámci Kubernetes instance. Pro usnadnění vaší práce a usnadňuje interakci s privátní služby z místního počítače připojení prostředí vytvoří dočasný tunelového propojení SSH ke kontejneru, který běží v Azure.
1. Když `mywebapi` připravené, otevřete prohlížeč na adresu místního hostitele. Měli byste vidět odpovědi z `mywebapi` služby ("Hello z mywebapi").


## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>Vytvoření žádosti o z *webfrontend* k *mywebapi*
Můžete teď napsat kód `webfrontend` , vytváří požadavek na `mywebapi`.
1. Přejít do okna VS Code pro `webfrontend`.
1. Přidejte tyto řádky kódu v horní části `server.js`:
```javascript
var request = require('request');
var propagateHeaders = require('./propagateHeaders');
```

3. *Nahraďte* kód pro `/api` obslužná rutina GET. Při zpracování požadavku, zase umožňuje volání `mywebapi`a vrátí výsledky z obou služeb.

```javascript
app.get('/api', function (req, res) {
    request({
        uri: 'http://mywebapi',
        headers: propagateHeaders.from(req) // propagate headers to outgoing requests
    }, function (error, response, body) {
        res.send('Hello from webfrontend and ' + body);
    });
});
```

Všimněte si, jak je zjišťování služby DNS Kubernetes' vzhledem k odkazování na služby jako `http://mywebapi`. **Kód v našem vývojového prostředí běží stejným způsobem, který se spustí v produkčním prostředí**.

V předchozím příkladu kódu využívá pomocné rutiny modulu s názvem `propagateHeaders`. Tato pomocná byl přidán do složky kódu v době jste spustili `vsce init`. `propagateHeaders.from()` Funkce rozšíří konkrétní hlaviček z existující http. Objekt IncomingMessage do objektu hlavičky pro odchozí požadavek. Ukážeme, jak později to usnadňuje produktivitu vývojového prostředí v rámci scénáře team.


## <a name="debug-across-multiple-services"></a>Ladění ve více službách
1. V tomto okamžiku `mywebapi` by měla být stále spuštěná pomocí ladicího programu připojen. Pokud není, stiskněte F5 v `mywebapi` projektu.
1. Nastavit zarážky ve výchozí GET `/` obslužné rutiny.
1. V `webfrontend` projektu, zarážku těsně před odešle požadavek GET na `http://mywebapi`.
1. Stiskněte F5 v `webfrontend` projektu.
1. Otevřete web app a krok prostřednictvím kódu v obou služeb. Webová aplikace by měl zobrazit zprávu zřetězených dvě služby: "Hello z webfrontend a Hello z mywebapi".


Skvělá práce! Nyní máte aplikace s více kontejnerů, kde může každý kontejner vyvinuté a nasazuje samostatně.

> [!div class="nextstepaction"]
> [Další informace o vývoj v týmu](get-started-nodejs-06.md)

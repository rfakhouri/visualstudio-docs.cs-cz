---
title: Vytvoření prostředí pro vývoj .NET Core s kontejnery pomocí Kubernetes v cloudu – krok 3 – vytvoření webové aplikace ASP.NET Core | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 72c7df0a82b91f7b4665b8b7e2cecdfc2eea26cf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31887749"
---
# <a name="get-started-on-connected-environment-with-net-core"></a>Začínáme v připojeném prostředí s .NET Core

Předchozí krok: [vytvořte Kubernetes vývojového prostředí v Azure](get-started-netcore-02.md)

## <a name="create-an-aspnet-core-web-app"></a>Vytvoření webové aplikace ASP.NET Core
Pokud máte [.NET Core](https://www.microsoft.com/net) nainstalován, můžete rychle vytvořit webové aplikace ASP.NET Core ve složce s názvem `webfrontend`.
```cmd
dotnet new mvc --name webfrontend
```

Alternativně **stáhnout ukázkový kód z Githubu** přechodem na https://github.com/Azure/vsce a vyberte **klonovat nebo stáhnout** ke stahování úložiště GitHub na vašem místním prostředí. Kód pro tato příručka je v `vsce/samples/dotnetcore/getting-started/webfrontend`.

[!INCLUDE[](includes/vsce-init.md)]

[!INCLUDE[](includes/ensure-env-created.md)]

[!INCLUDE[](includes/build-and-run-in-k8s-cli.md)]

## <a name="update-a-content-file"></a>Aktualizace obsahu souboru
Připojené prostředí není jenom o získání kód spuštěný v Kubernetes – jde o umožňuje rychle a interaktivně, najdete v části kódu změny se projeví až v prostředí Kubernetes v cloudu.

1. Vyhledejte soubor `./Views/Home/Index.cshtml` a proveďte úpravy v kódu HTML. Můžete například změnit řádku 70, který čte `<h2>Application uses</h2>` něco jako: `<h2>Hello k8s in Azure!</h2>`
1. Uložte soubor. Několik okamžiků později, v okně terminálu se zobrazí zpráva, že soubor v kontejneru spuštěné byla aktualizována.
1. Přejděte do prohlížeče a aktualizujte stránku. Měli byste vidět webovou stránku zobrazit aktualizované HTML.

Co se stalo? Úpravy souborů obsahu, jako je HTML a CSS, takže nevyžadují opakované kompilace ve webové aplikaci .NET Core, aktivní `vsce up` příkaz budou automaticky synchronizovat všechny změněné soubory obsahu do kontejneru spuštěné v Azure, a tím poskytuje rychlý způsob, jak zobrazit obsah úpravy.

## <a name="update-a-code-file"></a>Aktualizace souboru kódu
Aktualizuje se soubory kódu vyžaduje trochu další práci, protože aplikace .NET Core musí znovu sestavte a vytvořit aktualizované aplikačních binárních souborů.

1. V okně terminálu stiskněte `Ctrl+C` (Zastavit `vsce up`).
1. Otevření souboru kódu s názvem `Controllers/HomeController.cs`a upravit zprávu, která se zobrazí stránku o: `ViewData["Message"] = "Your application description page.";`
1. Uložte soubor.
1. Spustit `vsce up` v okně terminálu. 

Tím se znovu sestaví bitovou kopii kontejneru a opětovně nasadí Helm grafu. Pokud chcete zobrazit kód změny projeví ve spuštěné aplikaci, přejděte do nabídky o ve webové aplikaci.


Není dispozici i však *rychlejší metoda* pro vývoj kód, který jsme vám prozkoumat v další části. 
> [!div class="nextstepaction"]
> [Ladění kontejner v Kubernetes](get-started-netcore-04.md)


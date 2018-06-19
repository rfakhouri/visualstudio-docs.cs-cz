---
title: Vytvoření prostředí pro vývoj .NET Core s kontejnery pomocí Kubernetes v cloudu – krok 4 – ladění a kontejneru v Kubernetes | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 043052dec78251647a3ef12e0b612355b6334692
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31886290"
---
# <a name="get-started-on-connected-environment-with-net-core"></a>Začínáme v připojeném prostředí s .NET Core
 
Předchozí krok: [vytvoření základní webové aplikace ASP.NET](get-started-netcore-03.md)

[!INCLUDE[](includes/debug-intro.md)]

[!INCLUDE[](includes/init-debug-assets-vscode.md)]


## <a name="select-the-vsce-debug-configuration"></a>Vyberte konfiguraci ladění VSCE
1. Chcete-li otevřít zobrazení ladění, klikněte na ikonu ladění v **aktivity panelu** stranu VS Code.
1. Vyberte **.NET Core spuštění (VSCE)** jako aktivní ladicí konfiguraci.

![](media/debug-configuration.png)

> [!Note]
> Pokud nevidíte žádné připojené prostředí příkazy v příkazu palety, zajistěte, abyste měli [nainstalované VS Code rozšíření pro připojené prostředí](get-started-netcore-01.md#get-kubernetes-debugging-for-vs-code).


## <a name="debug-the-container-in-kubernetes"></a>Ladění kontejneru v Kubernetes
Stiskněte tlačítko **F5** k ladění kódu v Kubernetes.

Stejně jako u `up` příkaz kódu je synchronizované do vývojového prostředí a kontejner je vytvořené a nasazené na Kubernetes. Tentokrát samozřejmě ladicího programu je připojený ke kontejneru vzdálené.

[!INCLUDE[](includes/tip-vscode-status-bar-url.md)]

Nastavte zarážky v souboru kódu na straně serveru, například v rámci `Index()` v fungovat `Controllers/HomeController.cs` zdrojový soubor. Aktualizací stránky prohlížeče způsobí, že zarážek narazí.

Máte plný přístup k ladění informace stejně, jako kdybyste kód se provádí místně, jako je například zásobníku volání, místní proměnné, informace o výjimce, atd.

## <a name="edit-code-and-refresh"></a>Upravit kód a aktualizace
S ladicím programem aktivní Ujistěte se, upravit kód. Například změnit zprávu o stránku ve `Controllers/HomeController.cs`. 

```csharp
public IActionResult About()
{
    ViewData["Message"] = "My custom message in the About page.";
    return View();
}
```

Uložte soubor a v **podokna akce ladění**, klikněte na tlačítko **aktualizovat** tlačítko. 

![](media/debug-action-refresh.png)

Místo znovu sestavit a znovu nasazovat novou bitovou kopii kontejneru pokaždé, když jsou provedeny úpravy kódu, který bude často trvat velmi dlouho, připojené prostředí zkompiluje přírůstkově kódu v rámci kontejneru existující zajistit rychlejší smyčky upravit/debug.

Aktualizovat webovou aplikaci v prohlížeči a přejděte na stránku o. Měli byste vidět vaše vlastní zpráva se zobrazí v uživatelském rozhraní.

**Nyní máte metodu pro rychlé iterace v kódu a ladění přímo v Kubernetes!** V dalším kroku uvidíme jak jsme můžete vytvořit a kontejner druhé volání.

> [!div class="nextstepaction"]
> [Volání služby spuštěné v samostatných kontejneru](get-started-netcore-05.md)

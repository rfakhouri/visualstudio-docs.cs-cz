---
title: Vytvoření prostředí pro vývoj Node.js s kontejnery pomocí Kubernetes v cloudu – krok 4 – ladění a kontejneru v Kubernetes | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 2d1ec5fe0436b394083a247faa4519505aa21ceb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31888542"
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Začínáme v připojeném prostředí s Node.js

Předchozí krok: [v Kubernetes vytvořit kontejner Node.js](get-started-nodejs-03.md)

[!INCLUDE[](includes/debug-intro.md)]

[!INCLUDE[](includes/init-debug-assets-vscode.md)]


## <a name="select-the-vsce-debug-configuration"></a>Vyberte konfiguraci ladění VSCE
1. Chcete-li otevřít zobrazení ladění, klikněte na ikonu ladění v **aktivity panelu** stranu VS Code.
1. Vyberte **spustit Program (VSCE)** jako aktivní ladicí konfiguraci.

![](media/debug-configuration-nodejs.png)

> [!Note]
> Pokud nevidíte žádné připojené prostředí příkazy v příkazu palety, zajistěte, abyste měli [nainstalované VS Code rozšíření pro připojené prostředí](get-started-nodejs-01.md#get-kubernetes-debugging-for-vs-code).

## <a name="debug-the-container-in-kubernetes"></a>Ladění kontejneru v Kubernetes
Stiskněte tlačítko **F5** k ladění kódu v Kubernetes!

Podobně jako `up` příkaz kódu je při spuštění ladění a kontejner je vytvořené a nasazené na Kubernetes synchronizované do vývojového prostředí. Tentokrát samozřejmě ladicího programu je připojený ke kontejneru vzdálené.

[!INCLUDE[](includes/tip-vscode-status-bar-url.md)]

Nastavte zarážky v souboru kódu na straně serveru, například v rámci `app.get('/api'...` v `server.js`. Aktualizujte stránku prohlížeče nebo stiskněte tlačítko "indikované ho znovu a musí průchodu zarážkou a moct krok prostřednictvím kódu.

Máte plný přístup k ladění informace stejně, jako kdybyste kód se provádí místně, jako je například zásobníku volání, místní proměnné, informace o výjimce, atd.

## <a name="edit-code-and-refresh-the-debug-session"></a>Upravit kód a aktualizujte relaci ladění
S ladicím programem aktivní Ujistěte se, kód upravit; například upravte uvítací zprávu znovu:

```javascript
app.get('/api', function (req, res) {
    res.send('**** Hello from webfrontend running in Azure! ****');
});
```

Uložte soubor a v **podokna akce ladění**, klikněte na tlačítko **aktualizovat** tlačítko. 

![](media/debug-action-refresh-nodejs.png)

Místo znovu sestavit a znovu nasazovat novou bitovou kopii kontejneru pokaždé, když jsou provedeny úpravy kódu, který bude často trvat velmi dlouho, restartuje připojené prostředí proces Node.js mezi ladicí relace zajistit rychlejší smyčky upravit/debug.

Webové aplikace do prohlížeče nebo klikněte na tlačítko Aktualizovat *indikované ho znovu* tlačítko. Měli byste vidět vaše vlastní zpráva se zobrazí v uživatelském rozhraní.


## <a name="use-nodemon-to-develop-even-faster"></a>Pomocí NodeMon i rychlejší vývoj
*Nodemon* je Oblíbené nástroj, které používají vývojáři Node.js pro rychlý vývoj. Místo ručně restartovat uzel proces pokaždé, když se provádí úpravy kódu na straně serveru, se vývojáři často konfigurace projektu jejich uzlu tak, aby měl *nodemon* sledování změn souborů a automaticky restartuje procesu serveru. V tomto stylu pracovní vývojář právě aktualizuje svého prohlížeče po provedení kód upravit.

Abyste mohli používat stejné, produktivní vývoj pracovních postupů, které můžete využít při vývoji místně je záměr připojeném prostředí. Pro ilustraci vzorku `webfrontend` projektu byl nakonfigurován na použití *nodemon* (je nakonfigurovaný jako závislost vývojářů v `package.json`).

Zkuste následující postup:
1. Zastavení ladicího programu VS Code.
1. Klikněte na ikonu ladění v **aktivity panelu** stranu VS Code. 
1. Vyberte **připojit (VSCE)** jako aktivní ladicí konfiguraci.
1. Stiskněte F5.

V této konfiguraci kontejneru je nakonfigurován na spuštění *nodemon*. Pokud jsou provedeny úpravy kódu serveru, *nodemon* automaticky restartuje proces uzel je stejný jako při vývoji místně. 
1. Upravit uvítací zprávu znovu v `server.js`a soubor uložte.
1. Aktualizujte stránku prohlížeče, nebo klikněte na *indikované ho znovu* tlačítko, podívejte se na změny vstoupí v platnost!

**Nyní máte metodu pro rychlé iterace v kódu a ladění přímo v Kubernetes!** V dalším kroku uvidíme jak jsme můžete vytvořit a kontejner druhé volání.

> [!div class="nextstepaction"]
> [Volání služby spuštěné v samostatných kontejneru](get-started-nodejs-05.md)


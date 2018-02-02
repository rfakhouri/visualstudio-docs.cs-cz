---
title: "Začínáme s Node.js v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: a8e6c800ef036d0f6e8e5affae745e541a276284
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="getting-started-with-nodejs-in-visual-studio"></a>Začínáme s Node.js v sadě Visual Studio
V tomto kurzu Node.js vývoj pomocí sady Visual Studio pro vytvoříte jednoduchou webovou aplikaci Node.js, přidat kód, prozkoumat některé funkce integrovaného vývojového prostředí a spuštění aplikace. Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).  

## <a name="create-a-project"></a>Vytvoření projektu
Nejdřív vytvoříte projekt Node.js webové aplikace.

1. Open Visual Studio 2017.  

2. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .  

3. V **nový projekt** dialogové okno, v levém podokně rozbalte **JavaScript**, zvolte **Node.js**. V prostředním podokně vyberte **základní Azure Node.js Express 4 aplikační**, zvolte **OK**.   

     Pokud nevidíte **základní Azure Node.js Express 4 aplikační** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** Dialogové okno. Spustí instalační program Visual Studio. Vyberte **Node.js vývoj** zatížení, zvolte **upravit**. 

    Visual Studio vytvoří nové řešení a otevře projektu. **App.js** projektu soubor se otevře v editoru (levé podokno). Pokud nejste obeznámeni s projekty a řešení sady Visual Studio, najdete v části [rychlý start: vytvoření první aplikace Node.js pomocí Visual Studio](../ide/quickstart-nodejs.md).

## <a name="add-some-code"></a>Přidat kód

1. V Průzkumníku řešení (pravé podokno) otevřete složku, zobrazení a potom otevřete index.pug.

1. Nahraďte obsah následující kód.

    ```js
    extends layout

    block content
      h1= title
      p Welcome to #{title}
      script.
        var f1 = function() { document.getElementById('myImage').src='#{data.item1}' }
      script.
        var f2 = function() { document.getElementById('myImage').src='#{data.item2}' }
      script.
        var f3 = function() { document.getElementById('myImage').src='#{data.item3}' }

      button(onclick='f1()') One!
      button(onclick='f2()') Two!
      button(onclick='f3()') Three!
      p
      a: img(id='myImage' height='200' width='200' src='')
    ```

1. Ve složce trasy otevřete index.js.

1. Přidejte následující kód před voláním `router.get`:

    ```js
    var getData = function () {
        var data = {
            'item1': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg',
            'item2': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg',
            'item3': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg'
        }
        return data;
    }
    ````

1. Nahraďte `router.get` funkce volání následujícím kódem:

    ```js
    router.get('/', function (req, res) {
        res.render('index', { title: 'Express', "data" });
    });
    ```

1. Po `data`, typ `: get` a IntelliSense zobrazí funkce getData. Vyberte `getData`.

    ![Použití prvku IntelliSense](../nodejs/media/tutorial-nodejs-intellisense.png) 

1. Odstraňte čárku (`,`) před `"data"` a zobrazí zvýraznění syntaxe zelená na výrazu. Podržte ukazatel nad zvýraznění syntaxe.

    ![Chyba syntaxe zobrazení](../nodejs/media/tutorial-nodejs-syntax-checking.png) 

    Poslední řádek této zprávy vás informuje, že překladač JavaScript čárkou (`,`).

1. Klikněte **seznam chyb** kartě.

    Zobrazí upozornění a popis společně s číslo a název souboru a řádku.

    ![Seznam chyb zobrazit](../nodejs/media/tutorial-nodejs-error-list.png)

1. Opravte kód přidáním čárkou (`,`) před `"data"`.

## <a name="set-a-breakpoint"></a>Nastavit zarážky

1. V index.js klikněte v levém oddělovací mezery před následující řádek kódu pro nastavení zarážky:

    `res.render('index', { title: 'Express', "data": getData() });`

    Zarážky jsou nejvíce základní a základní funkci spolehlivé ladění. Zarážku Určuje, kde by měl Visual Studio pozastavit spuštěním kódu, můžete si prohlédněte hodnoty proměnných nebo chování paměti, nebo zda získávání větev kódu běží. 

    ![Nastavit zarážky](../nodejs/media/tutorial-nodejs-set-breakpoint.png) 

## <a name="run-the-application"></a>Spuštění aplikace

1. Vyberte cíl ladění na panelu nástrojů ladění.

    ![Vyberte cíl ladění](../nodejs/media/tutorial-nodejs-deploy-target.png) 

1. Stiskněte klávesu **Ctrl + F5** ke spuštění aplikace.

    Ladicí program se pozastaví u, které můžete nastavit zarážky. Teď si můžete prohlédnout stav vaší aplikace.

1. Pozastavte ukazatel myši nad `getData` zobrazíte její vlastnosti v datového tipu

    ![Zkontrolujte proměnné](../nodejs/media/tutorial-nodejs-inspect-variables.png)

1. Stiskněte klávesu **F5** pokračujte.

    Aplikace se otevře v prohlížeči.

    V okně prohlížeče se zobrazí "Express" jako nadpis a "Vítá Express" v prvním odstavci.

1. Klikněte na tlačítka pro zobrazení různých obrázků.

    ![Aplikace spuštěná v prohlížeči](../nodejs/media/tutorial-nodejs-running-in-browser.png)  

1. Otevřete okno interaktivní Node.js výběrem **zobrazení > ostatní okna > Node.js interaktivních okna**.

   ![Otevřete okno interaktivní Node.js](../nodejs/media/tutorial-nodejs-interactive-window.png)  

    Okno interaktivní podporuje všechno, co můžete provést v kódu, včetně použití `require()` příkazy. Kód na následujícím snímku obrazovky definuje proměnnou a zobrazuje umístění překladač Node.js.

   ![Interaktivní okno Node.js](../nodejs/media/tutorial-nodejs-interactive-window-example.png)  

1. Zavřete webový prohlížeč.  

## <a name="optional-publish-to-azure-app-service"></a>(Volitelné) Publikování do služby Azure App Service

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**.

   ![Publikování do služby Azure App Service](../nodejs/media/tutorial-nodejs-publish-to-azure.png)  

1. Zvolte **služby Microsoft Azure App Service**.

    V **služby App Service** dialogové okno, můžete přihlásit k účtu Azure a připojit k existující předplatných Azure.

1. Postupujte podle zbývajících kroků a vyberte předplatné, zvolte nebo vytvořte skupinu prostředků, zvolte nebo vytvořte roviny aplikaci služby a potom postupujte podle kroků při zobrazení výzvy k publikování v Azure. Další podrobné pokyny naleznete v tématu [publikovat na webu Azure pomocí nástroje nasazení webu](https://github.com/Microsoft/nodejstools/wiki/Publish-to-Azure-Website-using-Web-Deploy).

1. **Výstup** okně se zobrazí průběh na nasazení do Azure.

    Na úspěšné nasazení aplikace otevře v prohlížeči spuštění v Azure App Service. Klikněte na tlačítko Zobrazit bitovou kopii.

   ![Aplikaci spuštěnou ve službě Azure App Service](../nodejs/media/tutorial-nodejs-running-in-azure.png)  

Blahopřejeme k dokončení tohoto kurzu!

## <a name="next-steps"></a>Další kroky 

- Další informace o [Node.js Tools pro Visual Studio](https://github.com/Microsoft/nodejstools/wiki)  
- Další informace o [Visual Studio IDE](../ide/visual-studio-ide.md)  
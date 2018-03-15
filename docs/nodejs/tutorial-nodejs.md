---
title: "Vytvoření aplikace Node.js a Express - sady Visual Studio | Microsoft Docs"
description: "V tomto kurzu vytvoříte aplikaci Node.js a Express v sadě Visual Studio"
ms.custom: 
ms.date: 03/13/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-nodejs
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
ms.openlocfilehash: 05e10e6016c4a6791b5bc80ba6a05616c1edb0f6
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="tutorial-create-a-nodejs-and-express-app-in-visual-studio"></a>Kurz: Vytvoření Node.js a expresní aplikaci v sadě Visual Studio
V tomto kurzu pro vývoj sady Visual Studio pomocí Node.js a Express vytvořit jednoduchou webovou aplikaci Node.js, přidat kód, prozkoumejte některé funkce integrovaného vývojového prostředí a spuštění aplikace. Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).  

V tomto kurzu zjistíte, jak:
> [!div class="checklist"]
> * Vytvoření projektu Node.js
> * Přidat kód
> * Použití prvku IntelliSense
> * Spuštění aplikace
> * Stiskněte tlačítko zarážky

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalovanou sadu Visual Studio a zatížení vývoj Node.js.

    Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).

    Pokud potřebujete nainstalovat zatížení, ale už máte Visual Studio, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Vyberte **Node.js vývoj** zatížení, zvolte **upravit**.

* Musíte mít nainstalován modul runtime Node.js.

    Pokud nemáte nainstalováno, nainstalovat verzi LTS [Node.js](https://nodejs.org/en/download/) webu. Obecně platí Visual Studio automaticky rozpozná nainstalované runtime Node.js. Pokud je nainstalovaný modul runtime nerozpozná, můžete nakonfigurovat tak, aby odkazovaly nainstalovaný modul runtime na stránce vlastností projektu (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **vlastnosti**).

## <a name="create-a-project"></a>Vytvoření projektu
Nejdřív vytvoříte projekt Node.js webové aplikace.

1. Open Visual Studio 2017.  

1. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .  

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **JavaScript**a potom zvolte **Node.js**. V prostředním podokně vyberte **základní Azure Node.js Express 4 aplikační**a potom zvolte **OK**.   

     Pokud nevidíte **základní Azure Node.js Express 4 aplikační** šablony projektu, je nutné nainstalovat **Node.js vývoj** zatížení první. 

    Visual Studio vytvoří nové řešení a otevře projektu. *App.js* projektu soubor se otevře v editoru (levé podokno).

    - Zvýrazněná tučným písmem je váš projekt pomocí názvu, který jste zadali **nový projekt** dialogové okno. V systému souborů je reprezentována tento projekt *.njsproj* soubor ve složce projektu. Můžete nastavit vlastnosti a proměnných prostředí přidružený k projektu pravým tlačítkem na projekt a zvolením **vlastnosti**. Odezvy pomocí jiných nástrojů pro vývoj, můžete provést, protože soubor projektu neprovede vlastní změny ke zdroji projekt Node.js.

    - Na nejvyšší úrovni je řešení, které ve výchozím nastavení má stejný název jako projektu. Řešení, reprezentována *.sln* souboru na disku, je kontejner pro jeden nebo více souvisejících projekty.

    - Uzel npm zobrazuje všechny balíčky nainstalované npm. Pravým tlačítkem na uzel npm vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

    - Soubory, jako projektu *app.js* zobrazí na uzel projektu. *app.js* je spuštění souboru projektu.

1. Otevřete **npm** uzlu a ujistěte se, že všechny požadované npm balíčky jsou k dispozici.

    Pokud některý chybí (ikona vykřičník), kliknete pravým tlačítkem **npm** uzel a zvolte **nainstalovat chybějící balíčky npm**.

## <a name="add-some-code"></a>Přidat kód

1. V Průzkumníku řešení (pravé podokno), otevřete složku, zobrazení a pak otevřete *index.pug*.

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

1. Ve složce trasy, otevřete *index.js*.

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

## <a name="use-intellisense"></a>Použití prvku IntelliSense

1. V *index.js*, přejděte na řádek obsahující kód `res.render`.

1. Po `data` řetězce, zadejte `: get` a IntelliSense si ukážeme `getData` funkce. Vyberte `getData`.

    ![Použití prvku IntelliSense](../nodejs/media/tutorial-nodejs-intellisense.png) 

1. Odstraňte čárku (`,`) před `"data"` a zobrazí zvýraznění syntaxe zelená na výrazu. Podržte ukazatel nad zvýraznění syntaxe.

    ![Chyba syntaxe zobrazení](../nodejs/media/tutorial-nodejs-syntax-checking.png) 

    Poslední řádek této zprávy vás informuje, že překladač JavaScript čárkou (`,`).

1. Klikněte **seznam chyb** kartě.

    Zobrazí upozornění a popis společně s číslo a název souboru a řádku.

    ![Seznam chyb zobrazit](../nodejs/media/tutorial-nodejs-error-list.png)

1. Opravte kód přidáním čárkou (`,`) před `"data"`.

## <a name="set-a-breakpoint"></a>Nastavit zarážky

1. V *index.js*, klikněte v levém oddělovací mezery před následující řádek kódu pro nastavení zarážky:

    `res.render('index', { title: 'Express', "data": getData() });`

    Zarážky jsou nejvíce základní a základní funkci spolehlivé ladění. Zarážku Určuje, kde by měl Visual Studio pozastavit spuštěním kódu, můžete si prohlédněte hodnoty proměnných nebo chování paměti, nebo zda získávání větev kódu běží. 

    ![Nastavit zarážky](../nodejs/media/tutorial-nodejs-set-breakpoint.png) 

## <a name="run-the-application"></a>Spuštění aplikace

1. Vyberte cíl ladění na panelu nástrojů ladění.

    ![Vyberte cíl ladění](../nodejs/media/tutorial-nodejs-deploy-target.png) 

1. Stiskněte klávesu **F5** (**ladění** > **spustit ladění**) ke spuštění aplikace.

    Ladicí program se pozastaví u, které můžete nastavit zarážky. Teď si můžete prohlédnout stav vaší aplikace.

1. Pozastavte ukazatel myši nad `getData` zobrazíte její vlastnosti v datového tipu

    ![Zkontrolujte proměnné](../nodejs/media/tutorial-nodejs-inspect-variables.png)

1. Stiskněte klávesu **F5** (**ladění** > **pokračovat**) Chcete-li pokračovat.

    Aplikace se otevře v prohlížeči.

    V okně prohlížeče se zobrazí "Express" jako nadpis a "Vítá Express" v prvním odstavci.

1. Klikněte na tlačítka pro zobrazení různých obrázků.

    ![Aplikace spuštěná v prohlížeči](../nodejs/media/tutorial-nodejs-running-in-browser.png)  

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

V tomto kurzu jste zjistili, jak pro vytvoření a spuštění aplikace Node.js pomocí expresního a stiskněte tlačítko zarážku používání ladicího programu.

> [!div class="nextstepaction"]
> [Node.js Tools for Visual Studio](https://github.com/Microsoft/nodejstools)
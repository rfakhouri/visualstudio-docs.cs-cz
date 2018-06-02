---
title: Vytvoření Node.js a expresní aplikaci
description: V tomto kurzu vytvoříte aplikaci pomocí nástrojů Node.js Tools for Visual Studio.
ms.custom: ''
ms.date: 03/13/2018
ms.technology: vs-nodejs
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 207d5941527d51c18c6690166ef751b4782b481c
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34477246"
---
# <a name="tutorial-create-a-nodejs-and-express-app-in-visual-studio"></a>Kurz: Vytvoření Node.js a expresní aplikaci v sadě Visual Studio
V tomto kurzu pro vývoj sady Visual Studio pomocí Node.js a Express vytvořit jednoduchou webovou aplikaci Node.js, přidat kód, prozkoumejte některé funkce integrovaného vývojového prostředí a spuštění aplikace. Pokud jste si sadu Visual Studio ještě nenainstalovali, nainstalujte si ji zdarma [odtud](http://www.visualstudio.com).

V tomto kurzu se naučíte:
> [!div class="checklist"]
> * Vytvořit projekt Node.js
> * Přidat kód
> * Používání technologie IntelliSense
> * Spuštění aplikace
> * Stiskněte tlačítko zarážky

## <a name="prerequisites"></a>Požadavky

* Je nutné mít nainstalovanou sadu Visual Studio 2017 a úlohu Vývoj aplikací Node.js.

    Pokud jste si sadu Visual Studio ještě nenainstalovali, nainstalujte si ji zdarma [odtud](http://www.visualstudio.com).

    Pokud potřebujete nainstalovat úlohu, ale Visual Studio už máte, klikněte v dialogovém okně **Nový projekt** v levém podokně na odkaz **Otevřít instalační program pro Visual Studio**. Spustí se instalační program pro Visual Studio. Zvolte úlohu **Vývoj aplikací Node.js** a pak zvolte **Změnit**.

* Je nutné mít nainstalovaný modul runtime Node.js.

    Pokud ho nemáte nainstalovaný, nainstalujte si verzi LTS z webu [Node.js](https://nodejs.org/en/download/). Obecně platí, že Visual Studio automaticky rozpozná nainstalovaný modul runtime Node.js. Pokud se nainstalovaný modul runtime nerozpozná, můžete projekt nakonfigurovat na stránce vlastností pomocí odkazu na nainstalovaný modul runtime (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **Vlastnosti**).

    V tomto kurzu byla testována s Node.js 8.10.0.

## <a name="create-a-project"></a>Vytvoření projektu
Nejdřív vytvoříte projekt Node.js webové aplikace.

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

1. V dialogovém okně **Nový projekt** v levém podokně rozbalte položku **JavaScript** a zvolte **Node.js**. V prostředním podokně vyberte **základní Azure Node.js Express 4 aplikační** a potom zvolte **OK**.

     Pokud nevidíte **základní Azure Node.js Express 4 aplikační** šablony projektu, je nutné nainstalovat **Node.js vývoj** zatížení první.

    Visual Studio vytvoří nové řešení a otevře příslušný projekt. *App.js* projektu soubor se otevře v editoru (levé podokno).

    - Projekt je zvýrazněný tučným písmem a má název, který jste zadali v dialogovém okně **Nový projekt**. V systému souborů je tento projekt reprezentovaný souborem *.njsproj* ve složce projektu. Vlastnosti a proměnné prostředí přidružené k projektu můžete nastavit tak, že kliknete pravým tlačítkem na projekt a zvolíte **Vlastnosti**. Odezvy pomocí jiných nástrojů pro vývoj, můžete provést, protože soubor projektu neprovede vlastní změny ke zdroji projekt Node.js.

    - Na nejvyšší úrovni je řešení, které má ve výchozím nastavení stejný název jako příslušný projekt. Řešení, reprezentované na disku souborem *.sln*, je kontejner pro jeden nebo více souvisejících projektů.

    - Uzel npm zobrazuje všechny nainstalované balíčky npm. Po kliknutí pravým tlačítkem na uzel npm lze vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

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

    Předchozí kód přidá značku dynamicky generovat stránku HTML s názvem a uvítací zprávy. Stránka taky obsahuje kód, který zobrazí obrázek, který změní pokaždé, když klikněte tlačítko.

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

    Tento kód vytvoří datový objekt, který jsme předá dynamicky generovaném stránku HTML.

1. Nahraďte `router.get` funkce volání následujícím kódem:

    ```js
    router.get('/', function (req, res) {
        res.render('index', { title: 'Express', "data" });
    });
    ```
    
    Předchozí kód nastaví aktuální stránku pomocí objektu směrovač Express a vykreslí stránku, předá objekt názvu a data na stránku.

    K předvedení několik funkcí sady Visual Studio, jsme součástí chybu na řádek obsahující kód `res.render`. Musíme opravte chybu před spuštěním aplikace. Chybu opravte v další části.

## <a name="use-intellisense"></a>Používání technologie IntelliSense

1. V *index.js*, přejděte na řádek obsahující kód `res.render`.

1. Umístěte kurzor po `data` řetězce, zadejte `: get` a IntelliSense si ukážeme `getData` funkce. Vyberte `getData`.

    ![Používání technologie IntelliSense](../nodejs/media/tutorial-nodejs-intellisense.png)

1. Odstraňte čárku (`,`) před `"data"` a zobrazí zvýraznění syntaxe zelená na výrazu. Podržte ukazatel nad zvýraznění syntaxe.

    ![Chyba syntaxe zobrazení](../nodejs/media/tutorial-nodejs-syntax-checking.png)

    Poslední řádek této zprávy vás informuje, že překladač JavaScript čárkou (`,`).

1. Klikněte **seznam chyb** kartě.

    Zobrazí upozornění a popis společně s číslo a název souboru a řádku.

    ![Seznam chyb zobrazit](../nodejs/media/tutorial-nodejs-error-list.png)

1. Opravte kód přidáním čárkou (`,`) před `"data"`.

## <a name="set-a-breakpoint"></a>Nastavení zarážky

1. V *index.js*, klikněte v levém oddělovací mezery před následující řádek kódu pro nastavení zarážky:

    `res.render('index', { title: 'Express', "data": getData() });`

    Zarážky jsou základní a nejjednodušší funkcí spolehlivého ladění. Zarážka určuje, kde má Visual Studio spuštěný kód pozastavit, abyste mohli zkontrolovat hodnoty proměnných či chování paměti, nebo abyste zjistili, jestli se nějaká větev kódu spouští.

    ![Nastavení zarážky](../nodejs/media/tutorial-nodejs-set-breakpoint.png)

## <a name="run-the-application"></a>Spuštění aplikace

1. Vyberte cíl ladění na panelu nástrojů ladění.

    ![Vyberte cíl ladění](../nodejs/media/tutorial-nodejs-deploy-target.png)

1. Stiskněte klávesu **F5** (**ladění** > **spustit ladění**) ke spuštění aplikace.

    Ladicí program se pozastaví u, které můžete nastavit zarážky. Teď si můžete prohlédnout stav vaší aplikace.

1. Pozastavte ukazatel myši nad `getData` zobrazíte její vlastnosti v datového tipu

    ![Kontrola proměnných](../nodejs/media/tutorial-nodejs-inspect-variables.png)

1. Stiskněte klávesu **F5** (**ladění** > **pokračovat**) Chcete-li pokračovat.

    Aplikace se otevře v prohlížeči.

    V okně prohlížeče se zobrazí "Express" jako nadpis a "Vítá Express" v prvním odstavci.

1. Klikněte na tlačítka pro zobrazení různých obrázků.

    ![Aplikace spuštěná v prohlížeči](../nodejs/media/tutorial-nodejs-running-in-browser.png)

1. Zavřete webový prohlížeč.

## <a name="optional-publish-to-azure-app-service"></a>(Volitelné) Publikování do služby Azure App Service

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**.

   ![Publikování do Azure App Service](../nodejs/media/tutorial-nodejs-publish-to-azure.png)

1. Zvolte **služby Microsoft Azure App Service**.

    V **služby App Service** dialogové okno, můžete přihlásit k účtu Azure a připojit k existující předplatných Azure.

1. Postupujte podle zbývajících kroků a vyberte předplatné, zvolte nebo vytvořte skupinu prostředků, zvolte nebo vytvořte roviny aplikaci služby a potom postupujte podle kroků při zobrazení výzvy k publikování v Azure. Další podrobné pokyny naleznete v tématu [nasazení publikovat na webu Azure pomocí webových](https://github.com/Microsoft/nodejstools/wiki/Publish-to-Azure-Website-using-Web-Deploy).

1. **Výstup** okně se zobrazí průběh na nasazení do Azure.

    Na úspěšné nasazení aplikace otevře v prohlížeči spuštění v Azure App Service. Klikněte na tlačítko Zobrazit bitovou kopii.

   ![Aplikaci spuštěnou ve službě Azure App Service](../nodejs/media/tutorial-nodejs-running-in-azure.png)

Blahopřejeme k dokončení tohoto kurzu!

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste zjistili, jak pro vytvoření a spuštění aplikace Node.js pomocí expresního a stiskněte tlačítko zarážku používání ladicího programu.

> [!div class="nextstepaction"]
> [Node.js Tools for Visual Studio](https://github.com/Microsoft/nodejstools)
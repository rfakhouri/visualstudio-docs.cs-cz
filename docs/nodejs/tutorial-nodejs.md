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
ms.openlocfilehash: f3d8bb6eb64433ef8e2cd369ed0c1e0ba59a03dd
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282506"
---
# <a name="tutorial-create-a-nodejs-and-express-app-in-visual-studio"></a>Kurz: Vytvoření Node.js a expresní aplikaci v sadě Visual Studio
V tomto kurzu pro vývoj sady Visual Studio pomocí Node.js a Express vytvořit jednoduchou webovou aplikaci Node.js, přidat kód, prozkoumejte některé funkce integrovaného vývojového prostředí a spuštění aplikace. Pokud jste si sadu Visual Studio ještě nenainstalovali, nainstalujte si ji zdarma [odtud](http://visualstudio.microsoft.com).

V tomto kurzu se naučíte:
> [!div class="checklist"]
> * Vytvořit projekt Node.js
> * Přidat kód
> * Použijte pro úpravu kódu technologie IntelliSense
> * Spuštění aplikace
> * Stiskněte tlačítko zarážek v ladicím programu

## <a name="before-you-begin"></a>Než začnete

Zde je rychlý nejčastější dotazy k vám představí některé klíčové koncepty.

### <a name="what-is-nodejs"></a>Co je Node.js?

Platforma Node.js je prostředí runtime jazyka JavaScript na straně serveru, které provádí JavaScript na straně serveru.

### <a name="what-is-npm"></a>Co je npm?

npm je výchozí Správce balíčků pro Node.js. Správce balíčků je jednodušší pro programátory v jazyce k publikování a sdílení zdrojového kódu Node.js knihoven a slouží k instalaci, aktualizaci a odinstalaci knihoven zjednodušit.

### <a name="what-is-express"></a>Co je express?

Express je architektura webových aplikací, sloužit jako server rozhraní pro Node.js pro tvorbu webových aplikací. Express umožňuje používat zvolte jinou front-endové rozhraní pro vytvoření uživatelského rozhraní, jako je například Pug (dříve se označovaly jako Jade). V tomto kurzu se používá pug.

## <a name="prerequisites"></a>Požadavky

* Je nutné mít nainstalovanou sadu Visual Studio 2017 a úlohu Vývoj aplikací Node.js.

    Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

    Pokud potřebujete nainstalovat zatížení, ale už máte Visual Studio, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno (vyberte **soubor**  >  **Nové** > **projektu**). Spustí se instalační program pro Visual Studio. Zvolte úlohu **Vývoj aplikací Node.js** a pak zvolte **Změnit**.

* Je nutné mít nainstalovaný modul runtime Node.js.

    Pokud ho nemáte nainstalovaný, nainstalujte si verzi LTS z webu [Node.js](https://nodejs.org/en/download/). Obecně platí, že Visual Studio automaticky rozpozná nainstalovaný modul runtime Node.js. Pokud se nainstalovaný modul runtime nerozpozná, můžete projekt nakonfigurovat na stránce vlastností pomocí odkazu na nainstalovaný modul runtime (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **Vlastnosti**).

    V tomto kurzu byla testována s Node.js 8.10.0.

## <a name="create-a-new-nodejs-project"></a>Vytvořte nový projekt Node.js

Spravuje soubory pro jednu aplikaci v sadě Visual Studio *projektu*. Projekt obsahuje zdrojový kód, prostředky a konfiguračních souborů.

V tomto kurzu začnete s Jednoduchý projekt obsahující kód pro Node.js a expresní aplikaci.

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

1. V dialogovém okně **Nový projekt** v levém podokně rozbalte položku **JavaScript** a zvolte **Node.js**. V prostředním podokně vyberte **základní Azure Node.js Express 4 aplikační** a potom zvolte **OK**.

     Pokud nevidíte **základní Azure Node.js Express 4 aplikační** šablony projektu, je nutné nainstalovat **Node.js vývoj** zatížení první (viz požadavky na pokyny).

    Visual Studio vytvoří nové řešení a projekt se otevře v pravém podokně. *App.js* projektu soubor se otevře v editoru (levé podokno).

    ![Struktura projektu](../nodejs/media/tutorial-project-structure.png)

    (1) zvýrazněných v **tučné** je váš projekt pomocí názvu, který jste zadali **nový projekt** dialogové okno. V systému souborů je tento projekt reprezentovaný souborem *.njsproj* ve složce projektu. Vlastnosti a proměnné prostředí přidružené k projektu můžete nastavit tak, že kliknete pravým tlačítkem na projekt a zvolíte **Vlastnosti**. Odezvy pomocí jiných nástrojů pro vývoj, můžete provést, protože soubor projektu neprovede vlastní změny ke zdroji projekt Node.js.

    (2) na nejvyšší úrovni je řešení, které ve výchozím nastavení má stejný název jako projektu. Řešení, reprezentované na disku souborem *.sln*, je kontejner pro jeden nebo více souvisejících projektů.

    (3) npm uzlu se zobrazuje všechny balíčky nainstalované npm. Kliknete pravým tlačítkem na uzel npm Hledat a instalovat balíčky npm pomocí dialogové okno nebo instalace a aktualizace balíčků pomocí nastavení v *package.json* a klikněte pravým tlačítkem na možnosti v uzlu npm.

    (4) *package.json* je soubor používaný npm ke správě závislosti balíčků a verze balíčku pro místně nainstalované balíčky.

    (5) soubory projektu, jako *app.js* zobrazí na uzel projektu. *app.js* je spuštění souboru projektu a který je Proč se zobrazí v **tučné**. Spuštění souboru můžete nastavit tak, že kliknete pravým tlačítkem na soubor v projektu a výběr **nastavit jako spouštěcí soubor Node.js**.

1. Otevřete **npm** uzlu a ujistěte se, že všechny požadované npm balíčky jsou k dispozici.

    Pokud všechny balíčky jsou chybí (ikona vykřičník), kliknete pravým tlačítkem **npm** uzel a zvolte **nainstalovat chybějící balíčky npm**.

## <a name="add-some-code"></a>Přidat kód

Aplikace používá Pug pro rozhraní front-end JavaScript. Pug používá jednoduchý kód kód, který se zkompiluje do formátu HTML. (Pug je nastaven jako zobrazovací modul v *app.js*. Kód, který nastaví modul zobrazení v *app.js* je `app.set('view engine', 'pug');`.)

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

    Předchozí kód je používaný k dynamickému generování stránku HTML s názvem a uvítací zprávy. Stránka taky obsahuje kód, který zobrazí obrázek, který změní pokaždé, když klikněte tlačítko.

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

    Předchozí kód nastaví aktuální stránku pomocí objektu směrovač Express a vykreslí stránku, předá objekt názvu a data na stránku. *Index.pug* je zadán jako na při načtení stránky *index.js* běží. *index.js* je nakonfigurovaný jako výchozí trasu v *app.js* kódu (není vidět).

    K předvedení několik funkcí sady Visual Studio, jsme součástí chybu na řádek obsahující kód `res.render`. Musíme opravte chybu před spuštěním aplikace. Chybu opravte v další části.

## <a name="use-intellisense"></a>Používání technologie IntelliSense

IntelliSense je nástroj Visual Studio, který vám pomůže při psaní kódu.

1. V *index.js*, přejděte na řádek obsahující kód `res.render`.

1. Umístěte kurzor po `data` řetězce, zadejte `: get` a IntelliSense si ukážeme `getData` funkci definovanou dříve v kódu. Vyberte `getData`.

    ![Používání technologie IntelliSense](../nodejs/media/tutorial-nodejs-intellisense.png)

1. Odstraňte čárku (`,`) před `"data"` a zobrazí zvýraznění syntaxe zelená na výrazu. Podržte ukazatel nad zvýraznění syntaxe.

    ![Chyba syntaxe zobrazení](../nodejs/media/tutorial-nodejs-syntax-checking.png)

    Poslední řádek této zprávy vás informuje, že překladač JavaScript čárkou (`,`).

1. V dolním podokně, klikněte **seznam chyb** kartě.

    Zobrazí upozornění a popis společně s číslo a název souboru a řádku.

    ![Seznam chyb zobrazit](../nodejs/media/tutorial-nodejs-error-list.png)

1. Opravte kód přidáním čárkou (`,`) před `"data"`.

    Při opravě, řádku kódu by měl vypadat přibližně takto: `res.render('index', { title: 'Express', "data": getData() });`

## <a name="set-a-breakpoint"></a>Nastavení zarážky

Nyní klikněte na tlačítko spustit aplikaci pomocí ladicího programu sady Visual Studio, připojit. Před jsme to udělat, je potřeba nastavit zarážky.

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
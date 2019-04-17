---
title: Vytvoření Node.js a Express aplikace
description: V tomto kurzu vytvoříte aplikaci pomocí nástrojů Node.js Tools for Visual Studio.
ms.date: 09/24/2018
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 62f919551a13060bfd2b2d12726164902004d1bb
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59661708"
---
# <a name="tutorial-create-a-nodejs-and-express-app-in-visual-studio"></a>Kurz: Vytvoření Node.js a Express aplikace v sadě Visual Studio

V tomto kurzu pro vývoj sady Visual Studio pomocí Node.js a Express vytvořit jednoduchou webovou aplikaci Node.js, přidejte kód, prozkoumat některé funkce integrovaného vývojového prostředí a spuštění aplikace. 

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) stránku a nainstalovat zdarma.

::: moniker-end

V tomto kurzu se naučíte:
> [!div class="checklist"]
> * Vytvořit projekt Node.js
> * Přidání kódu
> * Pomocí technologie IntelliSense pro úpravu kódu
> * Spuštění aplikace
> * Na zarážku v ladicím programu

## <a name="before-you-begin"></a>Před zahájením

Tady je rychlý – nejčastější dotazy vám představí některé klíčové koncepty.

### <a name="what-is-nodejs"></a>Co je Node.js?

Node.js je prostředí runtime jazyka JavaScript na straně serveru, který se spustí JavaScript na straně serveru.

### <a name="what-is-npm"></a>Co je npm?

npm je výchozí Správce balíčků pro na Node.js. Správce balíčků usnadňuje práci programátorům k publikování a sdílet zdrojový kód z knihoven Node.js a je navržené pro zjednodušení instalace, aktualizace nebo odinstalace knihoven.

### <a name="what-is-express"></a>Co je express?

Express je architektura webových aplikací, použit jako architektura serveru pro Node.js k vytvoření webové aplikace. Express umožňuje používat zvolte různých front-endové rozhraní pro vytvoření uživatelského rozhraní, jako je například Pug (dříve se označovaly jako Jade). V tomto kurzu se používá pug.

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalovanou sadu Visual Studio a úlohy pro vývoj Node.js.

    ::: moniker range=">=vs-2019"
    Pokud jste ještě nenainstalovali aplikaci Visual Studio 2019, pokračujte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/) stránku a nainstalovat zdarma.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Pokud jste ještě nenainstalovali aplikaci Visual Studio 2017, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/) stránku a nainstalovat zdarma.
    ::: moniker-end

    Pokud je potřeba, nainstalujte úlohu, ale už máte sadu Visual Studio, přejděte na **nástroje** > **získat nástroje a funkce...** , který otevře instalačního programu sady Visual Studio. Zvolte úlohu **Vývoj aplikací Node.js** a pak zvolte **Změnit**.

    ![Úloha Node.js v instalačním programu VS](../ide/media/quickstart-nodejs-workload.png)

* Je nutné mít nainstalovaný modul runtime Node.js.

    Pokud ho nemáte nainstalovaný, nainstalujte si verzi LTS z webu [Node.js](https://nodejs.org/en/download/). Obecně platí, že Visual Studio automaticky rozpozná nainstalovaný modul runtime Node.js. Pokud se nainstalovaný modul runtime nerozpozná, můžete projekt nakonfigurovat na stránce vlastností pomocí odkazu na nainstalovaný modul runtime (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **Vlastnosti**).

    V tomto kurzu byl testován s využitím Node.js 8.10.0.

## <a name="create-a-new-nodejs-project"></a>Vytvořte nový projekt Node.js

Spravuje soubory pro jednu aplikaci v sadě Visual Studio *projektu*. Projekt obsahuje zdrojový kód, prostředky a konfigurační soubory.

V tomto kurzu začnete s Jednoduchý projekt obsahující kód pro Node.js a express aplikace.

1. Otevřít Visual Studio.

1. Vytvořte nový projekt.

    ::: moniker range=">=vs-2019"
    Stisknutím klávesy **Esc** zavřete okno start. Typ **Ctrl + Q** otevřete do vyhledávacího pole zadejte **Node.js**, klikněte na tlačítko **vytvořit novou aplikaci základní Azure Node.js Express 4** (JavaScript). V dialogovém okně, které se zobrazí, zvolte **vytvořit**.
    ::: moniker-end
    ::: moniker range="vs-2017"
    V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**. V levém podokně **nový projekt** dialogového okna rozbalte **JavaScript**, klikněte na tlačítko **Node.js**. V prostředním podokně vyberte **aplikace základní Azure Node.js Express 4**, klikněte na tlačítko **OK**.
    ::: moniker-end
    Pokud se nezobrazí **aplikace základní Azure Node.js Express 4** šablony projektu, je nutné přidat **vývoj v Node.js** pracovního vytížení. Podrobné pokyny najdete v tématu [požadavky](#prerequisites).

    Visual Studio vytvoří nové řešení a otevře projekt v pravém podokně. *App.js* soubor projektu se otevře v editoru (levé podokno).

    ![Struktura projektu](../javascript/media/tutorial-project-structure.png)

    (1) zvýrazněno **tučné** je váš projekt, pomocí názvu, který jste zadali v **nový projekt** dialogové okno. V systému souborů je tento projekt reprezentovaný souborem *.njsproj* ve složce projektu. Vlastnosti a proměnné prostředí přidružené k projektu můžete nastavit tak, že kliknete pravým tlačítkem na projekt a zvolíte **Vlastnosti**. Verzemi s jinými nástroji pro vývoj, můžete provést, protože soubor projektu není provádět vlastní změny zdroje projektu Node.js.

    (2) na nejvyšší úrovni je řešení, která ve výchozím nastavení má stejný název jako projekt. Řešení, reprezentované na disku souborem *.sln*, je kontejner pro jeden nebo více souvisejících projektů.

    (3) npm uzlu se zobrazuje všechny balíčky npm nainstalované. Kliknete pravým tlačítkem na uzel npm, který se má vyhledat a nainstalovat balíčky npm pomocí dialogové okno nebo instalace a aktualizace balíčků pomocí nastavení v *package.json* a klikněte pravým tlačítkem na možnosti v uzlu npm.

    (4) *package.json* je soubor používaný npm Spravovat závislosti balíčků a verze balíčku pro místně nainstalované balíčky. Další informace v tomto souboru najdete v tématu [konfigurační soubor package.json](../javascript/configure-packages-with-package-json.md)

    (5) soubory projektu, jako *app.js* zobrazí pod uzlem projektu. *app.js* je spouštěcí soubor projektu a, který je proč zobrazí v **tučné**. Můžete nastavit spouštěcí soubor tak, že kliknete pravým tlačítkem soubor v projektu a vyberete **nastavit jako spouštěcí soubor Node.js**.

1. Otevřít **npm** uzlu a ujistěte se, jestli jsou všechny balíčky npm vyžaduje k dispozici.

    Pokud všechny balíčky, které chybí (ikona vykřičník), kliknete pravým tlačítkem **npm** uzlu a zvolte **instalovat chybějící balíčky npm**.

## <a name="add-some-code"></a>Přidání kódu

Aplikace používá Pug pro front-endové rozhraní JavaScriptu. Pug používá jednoduchý kód kód, který se zkompiluje do formátu HTML. (Pug je nastaven jako zobrazovací modul v *app.js*. Kód, který nastaví modul zobrazení v *app.js* je `app.set('view engine', 'pug');`.)

1. V Průzkumníku řešení (pravé podokno), otevřete složku, zobrazení a pak otevřete *index.pug*.

1. Nahraďte obsah následujícím kódem.

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

    Předchozí kód se používá k dynamickému generování stránku HTML s názvem a zobrazení uvítací zprávy. Stránka také obsahuje kód, který zobrazí obrázek, který změní pokaždé, když stisknete tlačítko.

1. Ve složce trasy otevřete *index.js*.

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

    Tento kód vytvoří datový objekt, který můžete předat dynamicky generované stránky HTML.

1. Nahradit `router.get` funkce volání s následujícím kódem:

    ```js
    router.get('/', function (req, res) {
        res.render('index', { title: 'Express', "data" });
    });
    ```

    Předchozí kód nastaví aktuální stránku pomocí objektu směrovače Express a vykreslí stránku, předá objekt nadpis a data na stránce. *Index.pug* soubor zadaný jako na při načtení stránky *index.js* běží. *index.js* je nakonfigurovaný jako výchozí trasu v *app.js* kódu (nezobrazení).

    Abychom si předvedli několik funkcí sady Visual Studio, je rozhodnout vědomě a záměrně chyba na řádku kódu obsahující `res.render`. Je potřeba opravit chybu, než aplikace může běžet, které provedete v další části.

## <a name="use-intellisense"></a>Používání technologie IntelliSense

Technologie IntelliSense je nástroj sady Visual Studio, který vám pomůže vám při psaní kódu.

1. V *index.js*, přejděte na řádek obsahující kód `res.render`.

1. Umístěte kurzor po `data` řetězec, zadejte `: get` a technologie IntelliSense se seznámíte `getData` funkci definovanou dříve v kódu. Vyberte `getData`.

    ![Používání technologie IntelliSense](../javascript/media/tutorial-nodejs-intellisense.png)

1. Odstraňte čárku (`,`) před `"data"` a zobrazí se syntaxe zelené zvýraznění na výraz. Najeďte myší zvýraznění syntaxe.

    ![Chyba syntaxe zobrazení](../javascript/media/tutorial-nodejs-syntax-checking.png)

    Poslední řádek tato zpráva se říká, že interpreta jazyka JavaScript, očekávala se čárka (`,`).

1. Ve spodní části podokna klikněte na tlačítko **seznam chyb** kartu.

    Zobrazí upozornění a popis a název souboru a řádku počty.

    ![Zobrazení seznamu chyb](../javascript/media/tutorial-nodejs-error-list.png)

1. Kód opravit přidáním čárky (`,`) před `"data"`.

    Pokud opravíte, řádek kódu by měl vypadat nějak takto: `res.render('index', { title: 'Express', "data": getData() });`

## <a name="set-a-breakpoint"></a>Nastavení zarážky

Budete dále spusťte aplikaci v ladicím programu sady Visual Studio připojené. Než to provedete, je nutné nastavit zarážku.

1. V *index.js*, klikněte v levém hřbetu před následující řádek kódu pro nastavení zarážky:

    `res.render('index', { title: 'Express', "data": getData() });`

    Zarážky jsou základní a nejjednodušší funkcí spolehlivého ladění. Zarážka určuje, kde má Visual Studio spuštěný kód pozastavit, abyste mohli zkontrolovat hodnoty proměnných či chování paměti, nebo abyste zjistili, jestli se nějaká větev kódu spouští.

    ![Nastavení zarážky](../javascript/media/tutorial-nodejs-set-breakpoint.png)

## <a name="run-the-application"></a>Spuštění aplikace

1. Vyberte cíl ladění na panelu nástrojů ladění, jako je například Microsoft Edge nebo Chrome.

    ::: moniker range=">=vs-2019"
    ![Vyberte cíl ladění](../javascript/media/vs-2019/tutorial-nodejs-deploy-target.png)
    ::: moniker-end
    ::: moniker range="vs-2017"
    ![Vyberte cíl ladění](../javascript/media/tutorial-nodejs-deploy-target.png)
    ::: moniker-end

    Pokud je k dispozici na svém počítači Chrome, ale nezobrazí jako možnost, zvolte **procházet s** z rozevíracího seznamu cíl ladění a jako cíl výchozí prohlížeč vybrat Chrome (zvolte **nastavit jako výchozí**).

1. Stisknutím klávesy **F5** (**ladění** > **spustit ladění**) ke spuštění aplikace.

    Ladicí program pozastavení na zarážce, kterou jste nastavili. Teď si můžete prohlédnout stav vaší aplikace.

1. Najeďte myší na `getData` zobrazíte její vlastnosti v datovém tipu

    ![Kontrola proměnných](../javascript/media/tutorial-nodejs-inspect-variables.png)

1. Stisknutím klávesy **F5** (**ladění** > **pokračovat**) abyste mohli pokračovat.

    Aplikace se otevře v prohlížeči.

    V okně prohlížeče se zobrazí "Express" jako název a "Úvodní Express" v prvním odstavci.

1. Klepnutím na tlačítko zobrazit různé obrázky.

    ![Aplikace spuštěná v prohlížeči](../javascript/media/tutorial-nodejs-running-in-browser.png)

1. Zavřete webový prohlížeč.

## <a name="optional-publish-to-azure-app-service"></a>(Volitelné) Publikování do služby Azure App Service

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**.

   ![Publikování do Azure App Service](../javascript/media/tutorial-nodejs-publish-to-azure.png)

1. Zvolte **služby Microsoft Azure App Service**.

    V **služby App Service** dialogovém okně můžete přihlásit ke svému účtu Azure a připojit ke stávajícím předplatným Azure.

1. Postupujte podle pokynů vyberte předplatné, vyberte nebo vytvořte skupinu prostředků, zvolte nebo vytvoření app service roviny a pak postupujte podle kroků po zobrazení výzvy k publikování do Azure. Podrobnější pokyny najdete v článku [publikovat na webu Azure pomocí webu nasadit](https://github.com/Microsoft/nodejstools/wiki/Publish-to-Azure-Website-using-Web-Deploy).

1. **Výstup** okno zobrazí průběh na nasazení do Azure.

    Na úspěšné nasazení se aplikace otevře v prohlížeči ve službě Azure App Service. Kliknutím na tlačítko Zobrazit obrázek.

   ![Aplikace spuštěná ve službě Azure App Service](../javascript/media/tutorial-nodejs-running-in-azure.png)

Blahopřejeme k dokončení tohoto kurzu!

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Nasazení aplikace do služby App Service pro Linux](../javascript/publish-nodejs-app-azure.md)
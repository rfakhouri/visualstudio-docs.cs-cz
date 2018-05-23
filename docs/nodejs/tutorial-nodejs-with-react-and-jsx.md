---
title: Vytvoření aplikace Node.js a reagují
description: V tomto kurzu vytvoříte aplikaci pomocí Node.js tools pro Visual Studio
ms.custom: mvc
ms.date: 02/19/2018
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
ms.openlocfilehash: 9958711ea64daee9876d3b16330685786b6d5825
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2018
---
# <a name="tutorial-create-a-nodejs-and-react-app-in-visual-studio"></a>Kurz: Vytvoření aplikace Node.js a reagují v sadě Visual Studio
Visual Studio můžete snadno vytvořit projekt Node.js a využívat funkce IntelliSense a jiné integrované funkce, které podporují Node.js. V tomto kurzu pro sadu Visual Studio vytvořte projekt webové aplikace Node.js ze šablony sady Visual Studio. Pak vytvoříte jednoduchou aplikaci pomocí reagují.

V tomto kurzu zjistíte, jak:
> [!div class="checklist"]
> * Vytvoření projektu Node.js
> * Přidání balíčků npm
> * Přidat reagují kódu do vaší aplikace
> * Transpile JSX
> * Připojí ladicí program

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalované Visual Studio 2017 a zatížení vývoj Node.js.

    Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).

    Pokud potřebujete nainstalovat zatížení, ale už máte Visual Studio, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Vyberte **Node.js vývoj** zatížení, zvolte **upravit**.

* Musíte mít nainstalován modul runtime Node.js.

    Pokud nemáte nainstalováno, nainstalovat verzi LTS [Node.js](https://nodejs.org/en/download/) webu. Obecně platí Visual Studio automaticky rozpozná nainstalované runtime Node.js. Pokud je nainstalovaný modul runtime nerozpozná, můžete nakonfigurovat tak, aby odkazovaly nainstalovaný modul runtime na stránce vlastností projektu (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **vlastnosti**).

    V tomto kurzu byla testována s verze 8.9.4.

## <a name="create-a-project"></a>Vytvoření projektu
Nejprve vytvořte projekt webové aplikace Node.js.

1. Otevřete Visual Studio 2017.

1. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **JavaScript**a potom zvolte **Node.js**. V prostředním podokně vyberte **prázdnou webovou aplikaci Node.js**, zadejte název **NodejsWebAppBlank**a potom zvolte **OK**.

     Pokud nevidíte **prázdnou webovou aplikaci Node.js** šablony projektu, je nutné nejprve nainstalovat zatížení vývoj Node.js.

    Visual Studio vytvoří nové řešení a otevře projektu.

    ![Projekt Node.js v Průzkumníku řešení](../nodejs/media/tutorial-nodejs-react-project-structure.png)

    - Zvýrazněná tučným písmem je váš projekt pomocí názvu, který jste zadali **nový projekt** dialogové okno. V systému souborů je reprezentována tento projekt *.njsproj* soubor ve složce projektu. Můžete nastavit vlastnosti a proměnných prostředí přidružený k projektu pravým tlačítkem na projekt a zvolením **vlastnosti**. Můžete provést odezvy pomocí jiných nástrojů pro vývoj, protože soubor projektu neprovede vlastní změny ke zdroji projekt Node.js.

    - Na nejvyšší úrovni je řešení, které ve výchozím nastavení má stejný název jako projektu. Řešení, reprezentována *.sln* souboru na disku, je kontejner pro jeden nebo více souvisejících projekty.

    - Uzel npm zobrazuje všechny balíčky nainstalované npm. Pravým tlačítkem na uzel npm vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

    - Soubory, jako projektu *server.js* zobrazí na uzel projektu. *Server.js* je spuštění souboru projektu.

## <a name="add-npm-packages"></a>Přidání balíčků npm

Tato aplikace vyžaduje počet moduly npm správné fungování.

* Reagovat
* react-dom
* Express
* cesta
* zavaděč TS
* typescript
* webpack
* webpack-cli

1. V Průzkumníku řešení (pravé podokno) klikněte pravým tlačítkem myši **npm** uzlu v projektu a zvolte **nainstalovat nové balíčky npm**.

    V **nainstalovat nové balíčky npm** dialogové okno, můžete nainstalovat nejnovější verzi balíčku, nebo zadejte verzi. Pokud si zvolíte instalaci aktuální verze těchto balíčků, ale později spustit do neočekávaným chybám, budete muset nainstalujte přesné balíčku verze popsanou dále v těchto kroků.

1. V **nainstalovat nové balíčky npm** dialogové okno, vyhledejte balíček reagují a klikněte na tlačítko **instalovat balíček** k její instalaci.

    ![Instalovat balíčky npm](../nodejs/media/tutorial-nodejs-react-install-packages.png)

    **Výstup** okně se zobrazí průběh na instalaci balíčku. Při instalaci balíčku se zobrazí pod **npm** uzlu.

    Projektu *package.json* souboru je doplněné o nový balíček informace, včetně verze balíčku.

1. Místo použití uživatelského rozhraní k hledání a přidejte zbylé balíčků jeden po druhém, vložte následující kód do package.json. Nahraďte `dependencies` část s tímto kódem:

    ```js
    "dependencies": {
      "express": "4.16.2",
      "path": "0.12.7",
      "react": "16.2.0",
      "react-dom": "16.2.0",
      "ts-loader": "4.0.1",
      "typescript": "2.7.2",
      "webpack": "4.1.1",
      "webpack-cli": "2.0.11"
    }
    ```

1. Klikněte pravým tlačítkem na **npm** uzlu ve vašem projektu a zvolte **nainstalovat chybějící balíčky npm**.

    **Výstup** okno zobrazuje průběh instalace balíčků.

    Tady jsou moduly npm, jak se zobrazují v Průzkumníku řešení po jejich instalaci.

    ![balíčky npm](../nodejs/media/tutorial-nodejs-react-npm-modules.png)

    > [!NOTE]
    > Pokud ale chcete-li instalovat balíčky npm pomocí příkazového řádku, klikněte pravým tlačítkem na uzel projektu a zvolte **sem otevřete příkazový řádek**. Standardní příkazy Node.js použijte k instalaci balíčků.

## <a name="add-project-files"></a>Přidat soubory projektu

V následujícím postupu přidat čtyři nové soubory do projektu.

* *app.tsx*
* *webpack-config.js*
* *index.html*
* *tsconfig.json*

Pro tuto aplikaci jednoduché přidáte nové soubory projektu v kořenu projektu. (Ve většině aplikací, obvykle přidání souborů do podsložky a odpovídajícím způsobem upravit odkazuje na relativní cestu.)

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt **NodejsWebAppBlank** a zvolte **přidat** > **novou položku**.

1. V **přidat novou položku** dialogovém okně vyberte **TypeScript JSX soubor**, zadejte název *app.tsx*a klikněte na tlačítko **OK**.

1. Opakujte tyto kroky pro přidání *webpack config.js*.

1. Opakujte stejný postup pro přidání *index.html* do projektu. Místo souboru JavaScript, zvolte **soubor HTML**.

1. Opakujte stejný postup pro přidání *tsconfig.json* do projektu. Místo souboru JavaScript, zvolte **TypeScript JSON konfigurační soubor**.

## <a name="add-app-code"></a>Přidání kódu aplikace

1. Otevřete *server.js* a kódu nahraďte následujícím kódem:

    ```javascript
    'use strict';
    var path = require('path');
    var express = require('express');

    var app = express();

    var staticPath = path.join(__dirname, '/');
    app.use(express.static(staticPath));

    // Allows you to set port in the project properties.
    app.set('port', process.env.PORT || 3000);

    var server = app.listen(app.get('port'), function() {
        console.log('listening');
    });
    ```

   Předchozí kód používá spustit jako serveru vaší webové aplikace Node.js Express. Tento kód nastaví číslo portu ve vlastnostech projektu port (standardně port je konfigurován pro 1337 ve vlastnostech). Otevřete vlastnosti projektu, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a zvolte **vlastnosti**.

1. Otevřete *app.tsx* a přidejte následující kód:

    ```javascript
    declare var require: any

    var React = require('react');
    var ReactDOM = require('react-dom');

    class Hello extends React.Component {
        render() {
            return (
                <h1>Welcome to React!!</h1>
            );
        }
    }

    ReactDOM.render(<Hello />, document.getElementById('root'));
    ```

    Předchozí kód používá syntaxi JSX a reagují k zobrazení jednoduché zprávy.

1. Otevřete *index.html* a nahraďte **textu** oddíl následujícím kódem:

    ```html
    <body>
        <div id="root"></div>
        <!-- scripts -->
        <script src="./dist/app-bundle.js"></script>
    </body>
    ```

    Tato HTML stránka načte *aplikace bundle.js*, který obsahuje kód transpiled JSX a reagují na prostý JavaScript. V současné době *aplikace bundle.js* je soubor prázdný. V další části můžete konfiguraci možností a transpile kód.

## <a name="configure-webpack-and-typescript-compiler-options"></a>Konfigurace webpack a TypeScript – možnosti kompilátoru

V předchozích krocích jste přidali *webpack config.js* do projektu. Dál přidejte kód webpack konfigurace. Přidá jednoduché webpack konfigurace, která určuje vstupní soubor (*app.tsx*) a výstupní soubor (*aplikace bundle.js*) pro sdružování a transpiling JSX pro prostý jazyk JavaScript. Pro transpiling můžete taky nakonfigurovat některé možnosti kompilátoru TypeScript. Tento kód je základní konfigurace, která slouží jako úvod do webpack a TypeScript kompilátoru.

1. V Průzkumníku řešení otevřete *webpack config.js* a přidejte následující kód.

    ```json
    module.exports = {
        devtool: 'source-map',
        entry: "./app.tsx",
        mode: "development",
        output: {
            filename: "./app-bundle.js"
        },
        resolve: {
            extensions: ['.Webpack.js', '.web.js', '.ts', '.js', '.jsx', '.tsx']
        },
        module: {
            rules: [
                {
                    test: /\.tsx$/,
                    exclude: /(node_modules|bower_components)/,
                    use: {
                        loader: 'ts-loader'
                    }
                }
            ]
        }
    }
    ```

    Kód konfigurace webpack dá pokyn Webpack používat zavaděči TypeScript transpile JSX.

1. Otevřete tsconfig.json a přidejte následující kód, který určuje možnosti kompilátoru TypeScript:

    ```json
    {
      "compilerOptions": {
        "noImplicitAny": false,
        "module": "commonjs",
        "noEmitOnError": true,
        "removeComments": false,
        "sourceMap": true,
        "target": "es5",
        "jsx": "react"
      },
      "exclude": [
        "node_modules"
      ],
      "files": [
        "app.tsx"
      ]
    }
    ```

    app.tsx je zadán jako zdrojový soubor.

## <a name="transpile-the-jsx"></a>Transpile JSX

1. V Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu a zvolte **sem otevřete příkazový řádek**.

1. V příkazovém řádku zadejte následující příkaz:

    `node_modules\.bin\webpack app.tsx --config webpack-config.js`

    Okno příkazového řádku zobrazuje výsledek.

    ![Spustit webpack](../nodejs/media/tutorial-nodejs-react-run-webpack.png)

    Pokud se zobrazí chyby místo tento výstup, je nutné před odstranit vaše aplikace bude fungovat. Pokud vaše verze balíčku npm se liší od verze uvedené v tomto kurzu, který může být zdrojem chyb. Jeden způsob, jak opravit chyby, je použití přesné verze uvedené v dřívějších krocích. Navíc pokud jeden nebo více z těchto verzí balíčku je zastaralá a vede k chybě, můžete k instalaci novější verze a opravte chyby.

1. V Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu a zvolte **přidat** > **existující složku**, zvolte *dist* složky a klikněte na tlačítko  **Vyberte složku**.

    Visual Studio. přidá *dist* složky do projektu, který obsahuje *aplikace bundle.js* a *aplikace bundle.js.map*.

1. Otevřete *aplikace bundle.js* zobrazíte transpiled kódu jazyka JavaScript.

1. Pokud se zobrazí výzva k znovu načíst externě změněné soubory, klikněte na tlačítko **Ano všem**.

    ![Načíst změněné soubory](../nodejs/media/tutorial-nodejs-react-reload-files.png)

Pokaždé, když provedete změny *app.tsx*, je třeba znovu spustit příkaz webpack.

## <a name="run-the-app"></a>Spuštění aplikace

1. Ujistěte se, že Chrome je nastaven jako aktuální cíl ladění.

    ![Vyberte Chrome jako cíl ladění](../nodejs/media/tutorial-nodejs-react-debug-target.png)

1. Chcete-li spustit aplikaci, stiskněte **F5** (**ladění** > **spustit ladění**) nebo na tlačítko zelenou šipku.

    Otevře se okno konzoly Node.js zobrazující port, na kterém naslouchá ladicího programu.

    Visual Studio se spustí aplikace spuštěním souboru spuštění *server.js*.

    ![V prohlížeči spustit reagují](../nodejs/media/tutorial-nodejs-react-running-react.png)

1. Zavřete okno prohlížeče.

1. Zavřete okno konzoly.

## <a name="set-a-breakpoint-and-run-the-app"></a>Nastavit zarážky a spuštění aplikace

1. V *server.js*, klikněte do mřížky nalevo od `staticPath` deklarace pro nastavení zarážky:

    ![Nastavit zarážky](../nodejs/media/tutorial-nodejs-react-set-breakpoint.png)

    Zarážky jsou nejvíce základní a základní funkci spolehlivé ladění. Zarážku Určuje, kde by měl Visual Studio pozastavit spuštěním kódu, můžete si prohlédněte hodnoty proměnných nebo chování paměti, nebo zda získávání větev kódu běží.

1. Chcete-li spustit aplikaci, stiskněte **F5** (**ladění** > **spustit ladění**).

    Ladicí program pozastaví u zarážky sady (aktuální příkaz je označeno žlutě). Teď si můžete prohlédnout stav vaší aplikace podržením ukazatele nad proměnné, které jsou aktuálně v oboru, pomocí ladicího programu, jako **místní hodnoty –** a **sledovat** systému windows.

1. Stiskněte klávesu **F5** pokračujte aplikace.

1. Pokud chcete při použití nástroje pro vývojáře Chrome, stiskněte klávesu **F12**. Tyto nástroje můžete prozkoumat modelu DOM a interakci s aplikace pomocí konzoly pro JavaScript.

1. Zavřete webový prohlížeč a konzoly.

## <a name="set-and-hit-a-breakpoint-in-the-client-side-react-code"></a>Nastavit a stiskněte tlačítko zarážky v kódu reagují na straně klienta

V předchozím oddílu připojit ladicí program ke kódu Node.js na straně serveru. Připojí ladicí program ze sady Visual Studio a stiskněte tlačítko zarážky v kódu reagují na straně klienta, musí ladicí program Nápověda k identifikaci procesu správné. Tady je jeden způsob, jak povolit tuto funkci.

1. Zavřete všechna okna Chrome.

1. Otevřete **spustit** v systému Windows příkaz **spustit** tlačítko (klikněte pravým tlačítkem a zvolte **spustit**) a zadejte následující příkaz:

    `chrome.exe --remote-debugging-port=9222`

    Spustí se Chrome s povoleným laděním.

1. Přepněte do sady Visual Studio a nastavit zarážky *aplikace bundle.js* kód na `render()` fungovat, jak je znázorněno na následujícím obrázku:

    ![Nastavit zarážky](../nodejs/media/tutorial-nodejs-react-set-breakpoint-client-code.png)

1. Chrome vybrat jako cíl ladění v sadě Visual Studio, stiskněte klávesu **kombinaci kláves Ctrl + F5** (**ladění** > **spustit bez ladění**) a spusťte aplikaci v prohlížeči.

    Aplikace otevře novou kartu prohlížeče.

1. Zvolte **ladění** > **připojit k procesu**.

1. V **připojit k procesu** dialogové okno Vyberte **Webkit kód** v **připojit k** pole, zadejte **chrome** do pole Filtr pro filtrování výsledky hledání.

1. Vyberte proces Chrome s hostitelem správný port (1337 v tomto příkladu) a klikněte na **Attach**.

    ![Připojit k procesu](../nodejs/media/tutorial-nodejs-react-attach-to-process.png)

    Víte, že když Průzkumníka modelu DOM a konzoly pro JavaScript otevřete v sadě Visual Studio má správně připojen ladicí program. Tyto nástroje ladění jsou podobná Chrome Developer Tools a nástroje F12 pro okraj.

    > [!NOTE]
    > Pokud není připojit ladicí program a zobrazí se zpráva "nelze se připojit k procesu. Operace není právní v aktuálním stavu." pak pomocí Správce úloh zavřete všechny instance Chrome před zahájením Chrome v režimu ladění. Rozšíření Chrome může spuštění a zabráněním režimu úplné ladění.

1. Protože kód se zarážkou již spuštěn, aktualizujte stránku prohlížeče narazí zarážku.

    Při pozastavena v ladicím programu, můžete zkontrolovat stav vaší aplikace přesunutím ukazatele myši proměnné a pomocí ladicího programu. Ladicí program postoupíte podle krokování kódu (**F5**, **F10**, a **F11**).

    Můžete narazit zarážek buď *aplikace bundle.js* nebo její namapované umístění v *app.tsx*, v závislosti na vašem prostředí a prohlížeč stavu. V obou případech můžete krok prostřednictvím kódu a prozkoumat proměnné.

    * Pokud potřebujete rozdělit na kód v *app.tsx* a nelze provést, použijte **připojit k procesu** popsané v předchozích krocích připojit ladicí program. Otevřete dynamicky generovaném *app.tsx* soubor v Průzkumníku řešení otevřením **dokumentů skriptu** > **app.tsx**zarážku a aktualizovat stránku v prohlížeči.

        Případně pokud potřebujete rozdělit na kód v *app.tsx* a nelze provést, použijte `debugger;` příkaz v *app.tsx*, nebo místo toho nastavte zarážky v Chrome Developer Tools.

    * Pokud potřebujete rozdělit na kód v *aplikace bundle.js* a nelze provést, odstraňte daný soubor zdrojového mapování *aplikace bundle.js.map*.

    > [!TIP]
    > Po připojení k procesu poprvé pomocí následujících kroků, můžete rychle opět připojit do stejného procesu v aplikaci Visual Studio 2017 výběrem **ladění** > **připojte k procesu**.

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste zjistili, jak vytvořit aplikaci Node.js a reagují, transpile JSX a ladění. Další informace o Node.js Tools pro sadu Visual Studio, naleznete na stránce wikiwebu.

> [!div class="nextstepaction"]
> [Node.js Tools for Visual Studio](https://github.com/Microsoft/nodejstools)

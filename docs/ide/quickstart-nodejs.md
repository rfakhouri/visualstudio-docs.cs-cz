---
title: 'Rychlý start: Vytvořte svoji první aplikaci Node.js pomocí sady Visual Studio'
description: V tomto rychlém startu vytvoříte aplikaci Node.js v sadě Visual Studio
ms.date: 06/27/2018
ms.technology: vs-javascript
ms.topic: quickstart
ms.devlang: javascript
ms.assetid: b0e4ebed-1a01-41ef-aad1-4d8465ce5322
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 000d5f3cccdfda10ef90f5c752ec49ba29681435
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62953452"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-nodejs-app"></a>Rychlý start: Vytvořte svoji první aplikaci Node.js pomocí sady Visual Studio

V tomto úvodu 5 až 10 minut do integrovaného vývojového prostředí (IDE) sady Visual Studio vytvoříte jednoduchou webovou aplikaci Node.js.

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalovanou sadu Visual Studio a úlohy pro vývoj Node.js.

    ::: moniker range=">=vs-2019"
    Pokud jste ještě nenainstalovali aplikaci Visual Studio 2019, pokračujte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) stránku a nainstalovat zdarma.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Pokud jste ještě nenainstalovali aplikaci Visual Studio 2017, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.
    ::: moniker-end

    Pokud je potřeba, nainstalujte úlohu, ale už máte sadu Visual Studio, přejděte na **nástroje** > **získat nástroje a funkce...** , který otevře instalačního programu sady Visual Studio. Zvolte úlohu **Vývoj aplikací Node.js** a pak zvolte **Změnit**.

    ![Úloha Node.js v instalačním programu VS](../ide/media/quickstart-nodejs-workload.png)

* Je nutné mít nainstalovaný modul runtime Node.js.

    Pokud ho nemáte nainstalovaný, nainstalujte si verzi LTS z webu [Node.js](https://nodejs.org/en/download/). Obecně platí, že Visual Studio automaticky rozpozná nainstalovaný modul runtime Node.js. Pokud se nainstalovaný modul runtime nerozpozná, můžete projekt nakonfigurovat na stránce vlastností pomocí odkazu na nainstalovaný modul runtime (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **Vlastnosti**).

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt webové aplikace Node.js.

1. Pokud nemáte modul runtime Node.js, který je už nainstalovaný, nainstalujte verzi LTS z [Node.js](https://nodejs.org/en/download/) webu.

    Obecně platí, že Visual Studio automaticky rozpozná nainstalovaný modul runtime Node.js. Pokud se nainstalovaný modul runtime nerozpozná, můžete projekt nakonfigurovat na stránce vlastností pomocí odkazu na nainstalovaný modul runtime (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **Vlastnosti**).

1. Otevřít Visual Studio.

1. Vytvořte nový projekt.

    ::: moniker range=">=vs-2019"
    Stisknutím klávesy **Esc** zavřete okno start. Typ **Ctrl + Q** otevřete do vyhledávacího pole zadejte **Node.js**, klikněte na tlačítko **vytvořit nový projekt aplikace prázdná webová Node.js** (JavaScript). V dialogovém okně, které se zobrazí, zvolte **vytvořit**.
    ::: moniker-end
    ::: moniker range="vs-2017"
    V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**. V levém podokně **nový projekt** dialogového okna rozbalte **JavaScript**, klikněte na tlačítko **Node.js**. V prostředním podokně vyberte **prázdná webová aplikace Node.js**, klikněte na tlačítko **OK**.
    ::: moniker-end
    Pokud se nezobrazí **prázdná webová aplikace Node.js** šablony projektu, je nutné přidat **vývoj v Node.js** pracovního vytížení. Podrobné pokyny najdete v tématu [požadavky](#prerequisites).

    Visual Studio vytvoří a nového řešení a otevře projekt. *Server.js* otevře v editoru v levém podokně.

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE

1. Podívejte se na **Průzkumníka řešení** v pravém podokně.

   ![Průzkumník řešení](../ide/media/quickstart-nodejs-solution-explorer.png)

   - Projekt je zvýrazněný tučným písmem a má název, který jste zadali v dialogovém okně **Nový projekt**. Na disku, je reprezentována tento projekt *.njsproj* souboru ve složce vašeho projektu.

   - Na nejvyšší úrovni je řešení, které má ve výchozím nastavení stejný název jako příslušný projekt. Řešení, reprezentované na disku souborem *.sln*, je kontejner pro jeden nebo více souvisejících projektů.

   - Uzel npm zobrazuje všechny nainstalované balíčky npm. Po kliknutí pravým tlačítkem na uzel npm lze vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

1. Pokud chcete nainstalovat balíčky npm nebo příkazy Node.js z příkazového řádku, klikněte pravým tlačítkem na uzel projektu a zvolte **tady otevřete příkazový řádek**.

   ![Příkazový řádek Node.js](../ide/media/quickstart-nodejs-command-prompt.png)

1. V *server.js* souboru v editoru (levé podokno), zvolte `http.createServer` a potom stiskněte klávesu **F12** nebo zvolte **přejít k definici** (klikněte pravým tlačítkem) místní nabídce. Tento příkaz má definici typu `createServer` fungovat v *index.d.ts*.

   ![Přejít k definici kontextové nabídky](../ide/media/quickstart-nodejs-gotodefinition.png)

1. Vrácen do *server.js*, pak v tomto řádku kódu, umístěte kurzor na konec řetězce `res.end('Hello World\n');`a upravit ji tak, aby vypadal takto:

    `res.end('Hello World\n' + res.connection.`

    Můžete položit `connection.`, technologie IntelliSense poskytuje možnosti automatického dokončování položky kódu.

   ![Automatické dokončování IntelliSense](../ide/media/quickstart-nodejs-intellisense.png)

1. Zvolte **localPort**a pak zadejte `);` dokončete příkaz tak, aby vypadal takto:

    `res.end('Hello World\n' + res.connection.localPort);`

## <a name="run-the-application"></a>Spuštění aplikace

1. Stisknutím klávesy **Ctrl**+**F5** (nebo **ladit > Spustit bez ladění**) ke spuštění aplikace. Aplikace se otevře v prohlížeči.

1. V okně prohlížeče se zobrazí "Hello World" plus číslo místního portu.

1. Zavřete webový prohlížeč.

Blahopřejeme k dokončení tohoto rychlého startu, ve kterém jste začínal s Visual Studio IDE a Node.js. Pokud jste chtěli delve hlouběji do své možnosti, pokračujte kurz v **kurzy** část obsahu.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Nasazení aplikace do služby App Service pro Linux](../javascript/publish-nodejs-app-azure.md)

- [Kurz Node.js a Express](../javascript/tutorial-nodejs.md)
- [Kurz Node.js a React](../javascript/tutorial-nodejs-with-react-and-jsx.md)
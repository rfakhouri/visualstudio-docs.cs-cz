---
title: 'Rychlý úvod: Použití Visual Studio k vytvoření první aplikace Node.js'
description: V tento rychlý start můžete vytvořit aplikaci Node.js v sadě Visual Studio
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-nodejs
ms.topic: quickstart
ms.devlang: javascript
ms.assetid: b0e4ebed-1a01-41ef-aad1-4d8465ce5322
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 664eb75fb8fe105058ef78470245500e5e835515
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089274"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-nodejs-app"></a>Rychlý úvod: Použití Visual Studio k vytvoření první aplikace Node.js

V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou webovou aplikaci Node.js. Pokud jste ještě nenainstalovali Visual Studio 2017, přejděte k [Visual Studio stáhne](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejdřív vytvoříte projekt Node.js webové aplikace.

1. Pokud nemáte runtime Node.js již nainstalována, nainstalovat verzi LTS [Node.js](https://nodejs.org/en/download/) webu.

    Obecně platí, že Visual Studio automaticky rozpozná nainstalovaný modul runtime Node.js. Pokud se nainstalovaný modul runtime nerozpozná, můžete projekt nakonfigurovat na stránce vlastností pomocí odkazu na nainstalovaný modul runtime (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **Vlastnosti**).

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **JavaScript**, zvolte **Node.js**. V prostředním podokně vyberte **prázdné Node.js webové aplikace**, zvolte **OK**.

     Pokud nevidíte **prázdné Node.js webové aplikace** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí se instalační program pro Visual Studio. Zvolte úlohu **Vývoj aplikací Node.js** a pak zvolte **Změnit**.

     ![Node.js zatížení v instalační program VS](../ide/media/quickstart-nodejs-workload.png)

    Visual Studio vytvoří a nového řešení a otevře projektu. *Server.js* se otevře v editoru v levém podokně.

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE

1. Podívejte se na **Průzkumníku řešení** v pravém podokně.

   ![Průzkumník řešení](../ide/media/quickstart-nodejs-solution-explorer.png)

   - Projekt je zvýrazněný tučným písmem a má název, který jste zadali v dialogovém okně **Nový projekt**. Na disku, je reprezentována tento projekt *.njsproj* soubor ve složce projektu.

   - Na nejvyšší úrovni je řešení, které má ve výchozím nastavení stejný název jako příslušný projekt. Řešení, reprezentované na disku souborem *.sln*, je kontejner pro jeden nebo více souvisejících projektů.

   - Uzel npm zobrazuje všechny nainstalované balíčky npm. Po kliknutí pravým tlačítkem na uzel npm lze vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

1. Pokud chcete nainstalovat balíčky npm nebo node.js příkazy z příkazového řádku, klikněte pravým tlačítkem na uzel projektu a zvolte **sem otevřete příkazový řádek**.

   ![Node.js příkazového řádku](../ide/media/quickstart-nodejs-command-prompt.png)

1. V *server.js* souboru v editoru (levé podokno), zvolte `http.createServer` a potom stiskněte klávesu **F12** nebo zvolte **přejít k definici** z nabídky kontextu (klikněte pravým tlačítkem). Tento příkaz má definici `createServer` fungovat v *index.d.ts*.

   ![Přejít k definici kontextové nabídky](../ide/media/quickstart-nodejs-gotodefinition.png)

1. Získali zpět do *server.js*, pak v tomto řádku kódu, umístěte kurzor na konci řetězce `res.end('Hello World\n');`a upravit ji tak, aby vypadá takto:

    `res.end('Hello World\n' + res.connection.`

    Místo pro zadání `connection.`, IntelliSense poskytuje možnosti pro automatické dokončování položku kódu.

   ![Automatické dokončování IntelliSense](../ide/media/quickstart-nodejs-intellisense.png)

1. Zvolte **Místní_port**a pak zadejte `);` dokončit příkaz tak, aby vypadá takto:

    `res.end('Hello World\n' + res.connection.localPort);`

## <a name="run-the-application"></a>Spuštění aplikace

1. Stiskněte klávesu **Ctrl**+**F5** (nebo **ladění > Spustit bez ladění**) ke spuštění aplikace. Aplikace se otevře v prohlížeči.

1. V okně prohlížeče se zobrazí "Hello World" a číslem místního portu.

1. Zavřete webový prohlížeč.

Blahopřejeme k dokončení tento rychlý start, ve které jste získali začali s Visual Studio IDE a Node.js. Pokud chcete pustíte hlubší do jeho možnosti, pokračujte v kurzu **kurzy** části obsahu.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Nasazení aplikace do Azure App Service](..//deployment/quickstart-deploy-to-azure.md)

- [Kurz Node.js a Express](../nodejs/tutorial-nodejs.md)
- [Kurz Node.js a reagují](../nodejs/tutorial-nodejs-with-react-and-jsx.md)
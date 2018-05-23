---
title: 'Rychlý úvod: Použití Visual Studio k vytvoření první aplikace Node.js'
description: V tento rychlý start můžete vytvořit aplikaci Node.js v sadě Visual Studio
ms.date: 11/15/2017
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
ms.openlocfilehash: 0a78f9fdfd1ea3612d86432619c463d526eed5c2
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2018
---
# <a name="quickstart-use-visual-studio-to-create-your-first-nodejs-app"></a>Rychlý úvod: Použití Visual Studio k vytvoření první aplikace Node.js

V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou webovou aplikaci Node.js. Pokud jste ještě nenainstalovali Visual Studio 2017, přejděte k [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky instalaci zdarma.

## <a name="create-a-project"></a>Vytvoření projektu
Nejdřív vytvoříte projekt Node.js webové aplikace.

1. Pokud nemáte runtime Node.js již nainstalována, nainstalovat verzi LTS [Node.js](https://nodejs.org/en/download/) webu.

    Obecně platí Visual Studio automaticky rozpozná nainstalované runtime Node.js. Pokud je nainstalovaný modul runtime nerozpozná, můžete nakonfigurovat tak, aby odkazovaly nainstalovaný modul runtime na stránce vlastností projektu (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **vlastnosti**).

1. Otevřete Visual Studio 2017.

1. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu**.

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **JavaScript**, zvolte **Node.js**. V prostředním podokně vyberte **prázdné Node.js webové aplikace**, zvolte **OK**.

     Pokud nevidíte **prázdné Node.js webové aplikace** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Vyberte **Node.js vývoj** zatížení, zvolte **upravit**.

     ![Node.js zatížení v instalační program VS](../ide/media/quickstart-nodejs-workload.png)

    Visual Studio vytvoří a nového řešení a otevře projektu. *Server.js* se otevře v editoru v levém podokně.

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE

1. Podívejte se na **Průzkumníku řešení** v pravém podokně.

   ![Průzkumník řešení](../ide/media/quickstart-nodejs-solution-explorer.png)

  - Zvýrazněná tučným písmem je váš projekt pomocí názvu, který jste zadali **nový projekt** dialogové okno. Na disku, je reprezentována tento projekt *.njsproj* soubor ve složce projektu.

  - Na nejvyšší úrovni je řešení, které ve výchozím nastavení má stejný název jako projektu. Řešení, reprezentována *.sln* souboru na disku, je kontejner pro jeden nebo více souvisejících projekty.

  - Uzel npm zobrazuje všechny balíčky nainstalované npm. Pravým tlačítkem na uzel npm vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

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

Blahopřejeme k dokončení tento rychlý start! Věříme, že jste se naučili chvíli o prostředí Visual Studio IDE. Pokud chcete pustíte hlubší do jeho možnosti, pokračujte prosím se v kurzu **kurzy** části obsahu.

## <a name="next-steps"></a>Další kroky

- Projděte [kurzu Node.js a Express](../nodejs/tutorial-nodejs.md)
- Projděte [kurzu Node.js a reagují](../nodejs/tutorial-nodejs-with-react-and-jsx.md)
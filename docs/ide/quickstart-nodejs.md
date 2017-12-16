---
title: "Rychlý úvod: použijte sadu Visual Studio k vytvoření první aplikace Node.js | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: javascript
ms.assetid: b0e4ebed-1a01-41ef-aad1-4d8465ce5322
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs: JavaScript
ms.openlocfilehash: e08e08e760075fe250c294c59d4a072e2f529889
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/15/2017
---
# <a name="quickstart-use-visual-studio-to-create-your-first-nodejs-app"></a>Rychlý úvod: Použití Visual Studio k vytvoření první aplikace Node.js
V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou webovou aplikaci Node.js. Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).  

## <a name="create-a-project"></a>Vytvoření projektu
Nejdřív vytvoříte projekt Node.js webové aplikace.

1. Otevřete Visual Studio 2017.  

2. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .  

3. V **nový projekt** dialogové okno, v levém podokně rozbalte **JavaScript**, zvolte **Node.js**. V prostředním podokně vyberte **prázdné Node.js webové aplikace**, zvolte **OK**.   

     Pokud nevidíte **prázdné Node.js webové aplikace** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Vyberte **Node.js vývoj** zatížení, zvolte **upravit**.  

     ![Node.js zatížení v instalační program VS](../ide/media/quickstart-nodejs-workload.png)  

    Visual Studio vytvoří a nového řešení a otevře projektu. **Server.js** otevřen v editoru.

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE  

1. Podívejte se na **Průzkumníku řešení** v pravém podokně.

   ![Průzkumník řešení](../ide/media/quickstart-nodejs-solution-explorer.png)  

  - Zvýrazněná tučným písmem je váš projekt pomocí názvu, který jste zadali **nový projekt** dialogové okno. Na disku tento projekt je reprezentována .njsproj soubor ve složce projektu.

  - Na nejvyšší úrovni je řešení, které ve výchozím nastavení má stejný název jako projektu. Řešení, reprezentována soubor .sln na disku, je kontejner pro jednu nebo více souvisejících s projekty.

  - Uzel npm zobrazuje všechny balíčky nainstalované npm. Pravým tlačítkem na uzel npm vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

1. Pokud chcete nainstalovat balíčky npm nebo node.js příkazy z příkazového řádku, klikněte pravým tlačítkem na uzel projektu a zvolte **sem otevřete příkazový řádek**.

   ![Node.js příkazového řádku](../ide/media/quickstart-nodejs-command-prompt.png) 

1. V **server.js** souboru v editoru (levé podokno), zvolte `http.createServer` a potom stiskněte klávesu **F12** nebo zvolte **přejít k definici** z nabídky kontextu (klikněte pravým tlačítkem). Tento příkaz má definici `createServer` funkce v index.d.ts.  

   ![Přejít k definici kontextové nabídky](../ide/media/quickstart-nodejs-gotodefinition.png)  

1. V tomto řádku kódu, umístěte kurzor na konci řetězce `res.end('Hello World\n');`a upravit ji tak, aby vypadá takto:

    `res.end('Hello World\n' + res.connection.`

    Místo pro zadání `connection.`, IntelliSense poskytuje možnosti pro automatické dokončování položku kódu.

   ![Automatické dokončování IntelliSense](../ide/media/quickstart-nodejs-intellisense.png)  

1. Zvolte **Místní_port**a pak zadejte `);` dokončit příkaz tak, aby vypadá takto:

    `res.end('Hello World\n' + res.connection.localPort);`

## <a name="run-the-application"></a>Spuštění aplikace
1. Stiskněte klávesu **Ctrl + F5** (nebo **ladění > Spustit bez ladění**) ke spuštění aplikace. Aplikace se otevře v prohlížeči.  

1. V okně prohlížeče se zobrazí "Hello World" a číslem místního portu.

1. Zavřete webový prohlížeč.  

Blahopřejeme k dokončení tento rychlý start! Věříme, že jste se naučili chvíli o prostředí Visual Studio IDE. Pokud chcete pustíte hlubší do jeho možnosti, pokračujte prosím se v kurzu **kurzy** části obsahu.  

## <a name="next-steps"></a>Další kroky 

- Projděte [kurzu Node.js](../nodejs/tutorial-nodejs.md)  
- Další informace o [Visual Studio IDE](../ide/visual-studio-ide.md)  
- Další informace o [Node.js Tools pro Visual Studio](https://github.com/Microsoft/nodejstools/wiki)
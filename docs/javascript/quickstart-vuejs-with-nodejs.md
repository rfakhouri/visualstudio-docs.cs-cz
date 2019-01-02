---
title: 'Rychlý start: Vytvoření první aplikace pro Vue.js'
description: V tomto rychlém startu vytvoříte aplikaci Vue.js v sadě Visual Studio pomocí Node.js Tools for Visual Studio
ms.custom: seodec18
ms.date: 09/24/2018
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 61554a784c5e3f2abaa8987116854893408b2ded
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53853889"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-vuejs-app"></a>Rychlý start: Vytvoření první aplikace pro Vue.js pomocí sady Visual Studio

V tomto úvodu 5 až 10 minut do integrovaného vývojového prostředí (IDE) sady Visual Studio vytvoříte a spustí jednoduchou webovou aplikaci Vue.js. Pokud jste ještě nenainstalovali aplikaci Visual Studio 2017, přejděte [soubory ke stažení Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránku a nainstalovat zdarma.

> [!IMPORTANT]
> Tento článek vyžaduje Vue.js šablonu, která je k dispozici od verze Visual Studio 2017 verze 15.8.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt Vue.js webové aplikace.

1. Pokud nemáte modul runtime Node.js, který je už nainstalovaný, nainstalujte verzi LTS z [Node.js](https://nodejs.org/en/download/) webu.

    Obecně platí, že Visual Studio automaticky rozpozná nainstalovaný modul runtime Node.js. Pokud nezjistí nainstalovaný modul runtime, můžete nakonfigurovat tak, aby odkazovaly nainstalovaný modul runtime na stránce vlastností projektu (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **vlastnosti**).

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

1. V **nový projekt** dialogové okno, v části **JavaScript** > **Node.js** nebo **TypeScript**  >   **Node.js**, zvolte **základní webovou aplikaci Vue.js**. Zadejte název projektu a pak klikněte na tlačítko **OK**.

     ![VUE.js šablony](../javascript/media/vuejs-template.png)

    Visual Studio vytvoří nový projekt. Otevře se nový projekt v Průzkumníku řešení (pravé podokno).

     Pokud se nezobrazí **základní Vue.js webovou aplikaci** šablony projektu, klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí se instalační program pro Visual Studio. Zvolte úlohu **Vývoj aplikací Node.js** a pak zvolte **Změnit**.

     ![Úloha Node.js v instalačním programu VS](../ide/media/quickstart-nodejs-workload.png)

    Visual Studio vytvoří a nového řešení a otevře projekt.

1. Průběh instalace balíčků npm potřebnou pro aplikaci najdete v okně výstup (dolní podokno).

1. V Průzkumníku řešení otevřete **npm** uzlu a ujistěte se, zda jsou nainstalovány všechny balíčky uvedené npm.

    Pokud všechny balíčky, které chybí (ikona vykřičník), kliknete pravým tlačítkem **npm** uzlu a zvolte **instalovat chybějící balíčky npm**.

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE

1. Podívejte se na **Průzkumníka řešení** v pravém podokně.

     ![VUE.js řešení](../javascript/media/vuejs-solution.png)

   - Projekt je zvýrazněný tučným písmem a má název, který jste zadali v dialogovém okně **Nový projekt**. Na disku, je reprezentována tento projekt. *njsproj* souboru ve složce vašeho projektu.

   - Na nejvyšší úrovni je řešení, které má ve výchozím nastavení stejný název jako příslušný projekt. Řešení, reprezentovaný. *sln* souboru na disku, je kontejner pro jeden nebo více souvisejících projektů.

   - **Npm** uzlu se zobrazuje všechny balíčky npm nainstalované. Po kliknutí pravým tlačítkem na uzel npm lze vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

2. Pokud chcete nainstalovat balíčky npm nebo spustit příkazy Node.js z příkazového řádku, klikněte pravým tlačítkem na uzel projektu a zvolte **tady otevřete příkazový řádek**.

## <a name="add-a-vue-file-to-the-project"></a>Přidejte do projektu soubor .vue

1. V Průzkumníku řešení klikněte pravým tlačítkem na libovolné složky, jako *src/components* složky a klikněte na tlačítko **přidat** > **nová položka**.

1. Vyberte buď **komponenta jednoho souboru jazyka JavaScript Vue** nebo **TypeScript Vue jeden soubor součásti**a potom klikněte na tlačítko **přidat**.

    Visual Studio přidá nový soubor do projektu.

## <a name="build-the-project"></a>Sestavení projektu

1. (Pouze aplikace project TypeScript) Ze sady Visual Studio, zvolte **sestavení** > **Vyčistit řešení**.

1. Dále zvolte **sestavení** > **sestavit řešení** k sestavení projektu. Zkontrolujte **výstup** okno a zobrazit výsledky sestavení a zvolte **sestavení** z **zobrazit výstup z:** seznamu.

    Šablona projektu Vue.js používá `build` událost sestavení npm skript tím, že nakonfigurujete příspěvek. Pokud chcete toto nastavení změnit, otevřete soubor projektu (*\<projectname\>.njsproj*) z Průzkumníka Windows a vyhledejte tento řádek kódu:

    ```xml
    <PostBuildEvent>npm run build</PostBuildEvent>
    ```

## <a name="run-the-application"></a>Spuštění aplikace

1. Stisknutím klávesy **Ctrl**+**F5** (nebo **ladit > Spustit bez ladění**) ke spuštění aplikace.

   V konzole, zobrazí se zpráva *spuštění vývojového serveru*.

   Potom aplikace se otevře v prohlížeči.

   ![VUE.js aplikace spuštěná v prohlížeči](../javascript/media/vuejs-running-app.png)

1. Zavřete webový prohlížeč.

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli ještě něco o integrovaném vývojovém prostředí sady Visual Studio pomocí Vue.js. Pokud jste chtěli delve hlouběji do své možnosti, pokračujte kurz v **kurzy** část obsahu.

## <a name="next-steps"></a>Další kroky

- Projděte si [kurz Node.js a Express](../nodejs/tutorial-nodejs.md)
- Projděte si [kurz Node.js a React](/visualstudio/javascript/tutorial-nodejs-with-react-and-jsx)
- [Nasazení aplikace do služby App Service pro Linux](../javascript/publish-nodejs-app-azure.md)
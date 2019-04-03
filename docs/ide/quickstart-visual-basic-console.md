---
title: Vytvořte svoji první aplikaci konzoly pomocí jazyka Visual Basic
description: Zjistěte, jak vytvořit jednoduchou konzolovou aplikaci Hello World v sadě Visual Studio pomocí jazyka Visual Basic, krok za krokem.
ms.custom: seodec18
ms.date: 03/23/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: quickstart
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: d0ccaf648d4109679b7d1343df462ae4e8da3822
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856240"
---
# <a name="quickstart-create-your-first-console-app-in-visual-studio-with-visual-basic"></a>Rychlý start: Vytvoření první aplikace konzoly v sadě Visual Studio pomocí jazyka Visual Basic

V tomto úvodu 5 až 10 minut do integrovaného vývojového prostředí (IDE) sady Visual Studio vytvoříte jednoduchou aplikaci Visual Basic, která běží na konzole.

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) stránku a nainstalovat zdarma.

::: moniker-end

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt aplikace Visual Basic. Typ projektu obsahuje všechny soubory šablon, které potřebujete, než jste přidali ještě nic!

::: moniker range="vs-2017"

1. Otevřete Visual Studio 2017.

2. V horní nabídce zvolte **souboru** > **nový** > **projektu**.

3. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka Visual Basic**a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **Konzolová aplikace (.NET Core)**. Zadejte název projektu *HelloWorld*.

   ![Konzole šablonu projektu aplikace (.NET Core) v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](../ide/media/new-project-vb-dotnetcore-helloworld-console-app.png)

     Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony projektu, klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Klikněte na odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/vb-open-visual-studio-installer-hello-world.png)

     Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

     ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../ide/media/dot-net-core-xplat-dev-workload.png)

::: moniker-end

::: moniker range="vs-2019"

> [!NOTE]
> Některé z snímky obrazovky v tomto rychlém startu pomocí tmavý motiv. Pokud nepoužíváte tmavý motiv, ale chtěli, najdete v článku [přizpůsobit IDE sady Visual Studio a Editor](quickstart-personalize-the-ide.md) stránku a zjistěte, jak.

1. Open Visual Studio 2019.

1. V okně start zvolte **vytvořte nový projekt**.

   ![Zobrazit okno 'vytvořte nový projekt.](../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Na **vytvořte nový projekt** okno, zadejte nebo zadejte *konzoly* do vyhledávacího pole. Dále zvolte **jazyka Visual Basic** od jazyka seznamu a klikněte na tlačítko **Windows** ze seznamu platformy. 

   Po použití filtrů jazyka a libovolné platformy, zvolte **Konzolová aplikace (.NET Core)** šablony a klikněte na tlačítko **Další**.

   ![Výběr šablony jazyka Visual Basic pro aplikace konzoly (.NET Framework)](../get-started/visual-basic/media/vs-2019/vb-create-new-project-search-console-net-core-filtered.png)

   > [!NOTE]
   > Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony, můžete jej nainstalovat z **vytvořte nový projekt** okna. V **nenašli, co hledáte?** zprávu, zvolte **nainstalovat další nástroje a funkce** odkaz.
   >
   > ![Odkaz "Nainstalovat další nástroje a funkce" z 'Nemůžete najít, co hledáte' zprávy v okně "vytvořit nový projekt.](../get-started/media/vs-2019/not-finding-what-looking-for.png) 
   > 
   > Pak ve Visual Studio Installer, zvolte **vývoj pro různé platformy .NET Core** pracovního vytížení.
   >
   > ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../get-started/media/dot-net-core-xplat-dev-workload.png)
   >
   > Po tomto, zvolte **změnit** tlačítko v instalačním programu sady Visual Studio. Můžete být vyzváni k uložte svou práci; Pokud ano, udělejte to. Dále zvolte **pokračovat** instalace zatížení. Pak se vraťte ke kroku 2 v tomto "[vytvořte projekt](#create-a-project)" postup.

1. V **konfigurovat nový projekt** okno, zadejte nebo vložte *WhatIsYourName* v **název projektu** pole. Potom kliknutím na možnost **vytvořit**.

   ![v okně 'Konfigurovat nový projekt' pojmenujte svůj projekt "WhatIsYourName.](../get-started/visual-basic/media/vs-2019/vb-name-your-project-whatname.png)

   Visual Studio otevře nový projekt.

::: moniker-end

## <a name="create-the-application"></a>Vytvoření aplikace

Po výběru šablony projektu jazyka Visual Basic a pojmenujte svůj projekt, Visual Studio vytvoří jednoduchou aplikaci "Hello World". Volá <xref:System.Console.WriteLine%2A> metodu pro zobrazení řetězcový literál "Hello World!" v okně konzoly.

![Zobrazení kódu Hello World výchozí ze šablony](../ide/media/vb-console-helloworld-template.png)

Pokud kliknete **HelloWorld** tlačítko v integrovaném vývojovém prostředí, můžete program spustit v režimu ladění.

  ![Klikněte na tlačítko Hello World a spusťte program v režimu ladění](../ide/media/vb-console-hello-world-button.png)

Když toto provedete, v okně konzoly je viditelné jenom na chvíli předtím, než se toto okno zavře. Proto, `Main` metoda ukončí po jeho jediném příkazu, takže aplikace se ukončí.

### <a name="add-some-code"></a>Přidání kódu

Přidejme nějaký kód pozastavení aplikace a poté požádat pro uživatelský vstup.

1. Přidejte následující kód bezprostředně po volání <xref:System.Console.WriteLine%2A> metody:

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```

    Program to pozastaví, dokud stisknutím jakékoli klávesy.

2. Na panelu nabídek vyberte **sestavení** > **sestavit řešení**.

   Tento program zkompiluje do intermediate language (IL), která se převádí do binárního kódu, kompilátor just-in-time (JIT).

## <a name="run-the-application"></a>Spuštění aplikace

1. Klikněte na tlačítko **HelloWorld** tlačítko na panelu nástrojů.

   ![Klikněte na tlačítko Hello World a má program spustit z panelu nástrojů](../ide/media/vb-console-hello-world-button.png)

2. Stisknutím jakékoli klávesy zavřete okno konzoly.

   ![Okno Hello World konzoly a stisknutím libovolné klávesy pokračovat](../ide/media/vb-console-hello-world-press-any-key.png)

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli ještě něco o jazyce Visual Basic a Visual Studio IDE. Další informace najdete dál v následujícím kurzu.

> [!div class="nextstepaction"]
> [Začínáme s jazykem Visual Basic v sadě Visual Studio](../get-started/visual-basic/tutorial-console.md)

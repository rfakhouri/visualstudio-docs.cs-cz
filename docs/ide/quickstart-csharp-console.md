---
title: Pomocí sady Visual Studio k vytvoření vaší první C# Konzolová aplikace
titleSuffix: ''
description: Zjistěte, jak vytvořit jednoduchou konzolovou aplikaci Hello World v sadě Visual Studio s C#, krok za krokem.
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
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 34e943984755ff1f36f8a28134e1e2abde4312d4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62954044"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-c-console-app"></a>Rychlý start: Pomocí sady Visual Studio k vytvoření vaší první C# Konzolová aplikace

V tomto úvodu 5 až 10 minut do integrovaného vývojového prostředí (IDE) sady Visual Studio vytvoříte jednoduchou C# aplikaci, která běží na konzole.

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) stránku a nainstalovat zdarma.

::: moniker-end

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte aplikaci projektu jazyka C#. Typ projektu obsahuje všechny soubory šablon, které potřebujete, než jste přidali ještě nic!

::: moniker range="vs-2017"

1. Otevřete Visual Studio 2017.

2. V horní nabídce zvolte **souboru** > **nový** > **projektu**.

3. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka C#** a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **Konzolová aplikace (.NET Core)**. Zadejte název projektu *HelloWorld*.

   ![Konzole šablonu projektu aplikace (.NET Core) v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](../ide/media/new-project-csharp-dotnetcore-helloworld-console-app.png)

     Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony projektu, zvolte **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Zvolte odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/csharp-open-visual-studio-installer-hello-world.png)

     Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

     ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../ide/media/dot-net-core-xplat-dev-workload.png)

::: moniker-end

::: moniker range="vs-2019"

1. Open Visual Studio 2019.

1. V okně start zvolte **vytvořte nový projekt**.

   ![Okno 'vytvořte nový projekt.](../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Na **vytvořte nový projekt** okno, zadejte nebo zadejte *konzoly* do vyhledávacího pole. Dále zvolte **C#** od jazyka seznamu a klikněte na tlačítko **Windows** ze seznamu platformy. 

   Po použití filtrů jazyka a libovolné platformy, zvolte **Konzolová aplikace (.NET Core)** šablony a klikněte na tlačítko **Další**.

   ![Zvolte C# šablonu Konzolová aplikace (.NET Framework)](../get-started/csharp/media/vs-2019/csharp-create-new-project-search-console-net-core-filtered.png)

   > [!NOTE]
   > Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony, můžete jej nainstalovat z **vytvořte nový projekt** okna. V **nenašli, co hledáte?** zprávu, zvolte **nainstalovat další nástroje a funkce** odkaz.
   >
   > ![Odkaz "Nainstalovat další nástroje a funkce" z 'Nemůžete najít, co hledáte' zprávy v okně "vytvořit nový projekt.](../get-started/media/vs-2019/not-finding-what-looking-for.png) 
   > 
   > Pak ve Visual Studio Installer, zvolte **vývoj pro různé platformy .NET Core** pracovního vytížení.
   >
   > ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](./media/dot-net-core-xplat-dev-workload.png)
   >
   > Po tomto, zvolte **změnit** tlačítko v instalačním programu sady Visual Studio. Můžete být vyzváni k uložte svou práci; Pokud ano, udělejte to. Dále zvolte **pokračovat** instalace zatížení. Pak se vraťte ke kroku 2 v tomto "[vytvořte projekt](#create-a-project)" postup.

1. V **konfigurovat nový projekt** okno, zadejte nebo vložte *HelloWorld* v **název projektu** pole. Potom kliknutím na možnost **vytvořit**.

   ![v okně 'Konfigurace nového projektu' název projektu "Hello World"](../get-started/csharp/media/vs-2019/csharp-name-your-helloworld-project.png)

   Visual Studio otevře nový projekt.
   
::: moniker-end

## <a name="create-the-application"></a>Vytvoření aplikace

::: moniker range="vs-2017"

Po výběru šablony projektu C# a pojmenujte svůj projekt, Visual Studio vytvoří jednoduchou aplikaci "Hello World".

::: moniker-end

::: moniker range="vs-2019"

Visual Studio obsahuje výchozí kód "Hello World" v projektu.

::: moniker-end

(K tomu, které volá <xref:System.Console.WriteLine%2A> metodu pro zobrazení řetězcový literál "Hello World!" v okně konzoly.)

   ![Zobrazení kódu Hello World výchozí ze šablony](../ide/media/csharp-console-helloworld-template.png)

Pokud stisknete **F5**, spustíte program v režimu ladění. V okně konzoly se však viditelné jenom na chvíli předtím, než se toto okno zavře.

(Toto chování se stane, protože `Main` metoda ukončí po jeho jediném příkazu, takže aplikace se ukončí.)

### <a name="add-some-code"></a>Přidání kódu

Přidejme nějaký kód pozastavte aplikaci tak, aby v okně konzoly se nepodporuje zavřít, dokud nestisknete klávesu **ENTER**.

1. Přidejte následující kód bezprostředně po volání <xref:System.Console.WriteLine%2A> metody:

   ```csharp
   Console.ReadLine();
   ```

1. Ověřte, že to vypadá to v editoru kódu:

   ![Přidejte kód pro pozastavení aplikace Hello World](../ide/media/csharp-console-helloworld-add-code.png)

## <a name="run-the-application"></a>Spuštění aplikace

1. Zvolte **HelloWorld** tlačítko na panelu nástrojů ke spuštění aplikace v režimu ladění. (Nebo stisknutím klávesy **F5**.)

   ![Klikněte na tlačítko Hello World a spusťte tak aplikaci z panelu nástrojů](../ide/media/csharp-console-hello-world-button.png)

1. Zobrazení vaší aplikace v okně konzoly.

   ![Okna konzoly zobrazuje Hello World!](../ide/media/csharp-console-hello-world.png)

### <a name="close-the-application"></a>Zavřít aplikaci

1. Stisknutím klávesy **ENTER** zavřete okno konzoly.

1. Zavřít **výstup** podokno v sadě Visual Studio.

   ![Zavřete podokno výstup v sadě Visual Studio](../ide/media/csharp-hello-world-close-output-pane.png)

1. Zavřete Visual Studio.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli ještě něco o jazyce C# a Visual Studio IDE. Další informace najdete v následujících kurzech pokračujte.

> [!div class="nextstepaction"]
> [Začínáme s aplikaci konzoly C# v sadě Visual Studio](../get-started/csharp/tutorial-console.md)

---
title: "Rychlý úvod: Vytvoření první aplikace konzoly v sadě Visual Studio s jazykem Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 12/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: ghogen
dev_langs: vb
ms.openlocfilehash: 330594aaccbd691a548fec9c237de91d471f4020
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/15/2017
---
# <a name="quickstart-create-your-first-console-app-in-visual-studio-with-visual-basic"></a>Rychlý úvod: Vytvoření první aplikace konzoly v sadě Visual Studio s jazykem Visual Basic
V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou aplikaci jazyka Visual Basic, která běží na konzole.

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky instalaci zdarma.

## <a name="create-a-project"></a>Vytvoření projektu
Nejdřív vytvoříte projekt aplikace Visual Basic. Typ projektu se dodává s všechny soubory šablony, které budete potřebovat, než jste přidali i nic!

1. Otevřete Visual Studio 2017.

2. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .

3. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka Visual Basic**a potom zvolte **.NET Core**. V prostředním podokně vyberte **konzolové aplikace (.NET Core)**. Zadejte název projektu *HelloWorld*.

   ![Konzole šablony projektu aplikace (.NET Core) v dialogovém okně Nový projekt v prostředí Visual Studio IDE](../ide/media/new-project-vb-dotnetcore-helloworld-console-app.png)

     Pokud nevidíte **konzolové aplikace (.NET Core)** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Klikněte na odkaz otevřete instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/vb-open-visual-studio-installer-hello-world.png)

     Spustí instalační program Visual Studio. Vyberte **vývoj pro různé platformy .NET Core** zatížení a potom zvolte **upravit**.

     ![Vývoj pro různé platformy zatížení .NET core v instalačním programu Visual Studio](../ide/media/dot-net-core-xplat-dev-workload.png)

## <a name="create-the-application"></a>Vytvoření aplikace
Po výběru vaše šablona projektu jazyka Visual Basic a název projektu, Visual Studio vytvoří jednoduchou aplikaci "Hello World". Zavolá [Console.WriteLine(System.String)](https://docs.microsoft.com/en-us/dotnet/api/system.console.writeline?view=netframework-4.7.1#System_Console_WriteLine_System_String) metodu pro zobrazení řetězcového literálu "Hello, World!" v okně konzoly.

![Zobrazit ve výchozím kódu Hello, World ze šablony](../ide/media/vb-console-helloworld-template.png)

Pokud kliknete **HelloWorld** tlačítko v integrovaném vývojovém prostředí, můžete spustit program v režimu ladění.

  ![Klikněte na tlačítko Hello, World ke spuštění programu v režimu ladění](../ide/media/vb-console-hello-world-button.png)

Když to uděláte, v okně konzoly je viditelná jenom na chvíli, než toto okno zavře. K tomu dojde, protože `Main` metoda ukončí po provedení jeho jediný příkaz, a tudíž ukončení aplikace.

### <a name="add-some-code"></a>Přidat kód
Přidejme nějaký kód pozastavení aplikace a pak požádejte na vstup uživatele.

1. Přidejte následující kód ihned po volání [Console.WriteLine(System.String)](https://docs.microsoft.com/en-us/dotnet/api/system.console.writeline?view=netframework-4.7.1#System_Console_WriteLine_System_String) metoda:

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   Tento skript pozastaví program dokud stisknutí klávesy.

2. Na panelu nabídek vyberte **sestavení** > **sestavit řešení**.

   To zkompiluje vaším programem do převodní jazyk (IL), který je převést na binární kód kompilátorem v běhu (JIT).

## <a name="run-the-application"></a>Spuštění aplikace
1. Klikněte **HelloWorld** tlačítka na panelu nástrojů.

   ![Klikněte na tlačítko Hello World se spustit program z panelu nástrojů](../ide/media/vb-console-hello-world-button.png)

2. Stisknutím libovolné klávesy zavřete okno konzoly.

   ![Okně zobrazující Hello, World konzoly a stisknutím libovolné klávesy pokračujte](../ide/media/vb-console-hello-world-press-any-key.png)

Blahopřejeme k dokončení tento rychlý start! Věříme, že jste se dozvěděli, chvíli o jazyka Visual Basic a Visual Studio IDE. Pokud chcete pustíte hlubší, pokračujte prosím se v kurzu **kurzy** části obsahu.

## <a name="see-also"></a>Viz také
* [Rychlý úvod: Vytvoření "Hello World" Windows Forms aplikace v jazyce Visual Basic pomocí sady Visual Studio](quickstart-visual-basic-winforms.md)
* [Kurz: Začínáme s jazykem Visual Basic v sadě Visual Studio](tutorial-visual-basic-console.md)
* [IntelliSense pro soubory s kódem jazyka Visual Basic](visual-basic-specific-intellisense.md)

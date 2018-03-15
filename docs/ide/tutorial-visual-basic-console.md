---
title: "Začínáme s jazykem Visual Basic v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 12/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: tutorial
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: ghogen
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 3df1f9c2f7fc2af97bc5541d313df58da5907cea
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="getting-started-with-visual-basic-in-visual-studio"></a>Začínáme s jazykem Visual Basic v sadě Visual Studio
V tomto kurzu pro Visual Basic (VB) budete používat Visual Studio k vytvoření a spuštění aplikace několik různých konzoly a prozkoumat některé funkce sady Visual Studio [integrované vývojové prostředí (IDE)](visual-studio-ide.md) při uděláte.

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky instalaci zdarma.

## <a name="before-you-begin"></a>Než začnete
Zde je rychlý nejčastější dotazy k vám představí některé klíčové koncepty.
### <a name="what-is-visual-basic"></a>Novinky jazyka Visual Basic
Visual Basic je bezpečnost typů programovací jazyk, který je navržená tak, aby se snadno Další. Je odvozen od BASIC, což znamená "Začátečníka všechny účely symbolický instrukce kódu".
### <a name="what-is-visual-studio"></a>Co je Visual Studio?
Visual Studio je sada integrované vývojové kancelářské nástroje pro vývojáře. Považujte ho za programu, které můžete použít k vytvoření programy a aplikace.  
### <a name="what-is-a-console-app"></a>Co je konzola aplikace?
Konzolové aplikace přebírá vstup a také znám jako zobrazí výstup v okně příkazového řádku do konzoly.
### <a name="what-is-net-core"></a>Co je .NET Core?
.NET core je dalším krokem evolučním rozhraní .NET Framework. Kde rozhraní .NET Framework povoleno, abyste sdílet kódu v rámci programovací jazyky .NET Core přidá možnost sdílet kód napříč platformami. I lépe je open source. (Rozhraní .NET Framework a .NET Core zahrnují knihovny předkompilované funkce, jakož i modul common language runtime (CLR), která funguje jako virtuální počítač, ve kterém pro spouštění vašeho kódu.)

## <a name="start-developing"></a>Začít vyvíjet
Jste připravení začít vyvíjet? Jdeme!

### <a name="create-a-project"></a>Vytvoření projektu
Nejdříve vytvoříme projekt aplikace Visual Basic. Typ projektu se dodává s všechny soubory šablony, které budete potřebovat, než jste přidali i nic!

1. Open Visual Studio 2017.

2. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .

3. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka Visual Basic**a potom zvolte **.NET Core**. V prostředním podokně vyberte **konzolové aplikace (.NET Core)**. Potom zadejte název souboru *HelloWorld*.  

   ![Konzole šablony projektu aplikace (.NET Core) v dialogovém okně Nový projekt v prostředí Visual Studio IDE](../ide/media/new-project-vb-dotnetcore-whatisyourname-console-app.png)

#### <a name="add-a-workgroup-optional"></a>Přidat pracovní skupiny (volitelné)
Pokud nevidíte **konzolové aplikace (.NET Core)** šablony projektu, můžete ho získat tak, že přidáte **vývoj pro různé platformy .NET Core** zatížení. Můžete přidat tímto zatížením v jednom z následujících způsobů, v závislosti na tom, které instalují aktualizace Visual Studio 2017 na váš počítač.

##### <a name="option-1-use-the-new-project-dialog-box"></a>Možnost 1: Pomocí dialogového okna Nový projekt
1. Klikněte **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

  ![Klikněte na odkaz otevřete instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/vs-open-visual-studio-installer-generic.png)

2. Spustí instalační program Visual Studio. Vyberte **vývoj pro různé platformy .NET Core** zatížení a potom zvolte **upravit**.

   ![Vývoj pro různé platformy zatížení .NET core v instalačním programu Visual Studio](../ide/media/dot-net-core-xplat-dev-workload.png)

##### <a name="option-2-use-the-tools-menu-bar"></a>Možnost 2: Pomocí nabídky panelu nástrojů
1. Zrušit mimo **nový projekt** dialogové okno a z panelu horní nabídce zvolte **nástroje** > **funkcí a nástrojů pro získání...** .

2. Spustí instalační program Visual Studio. Vyberte **vývoj pro různé platformy .NET Core** zatížení a potom zvolte **upravit**.   

## <a name="create-a-what-is-your-name-application"></a>Vytvořit aplikaci "Co je název vašeho"
Umožňuje vytvořit aplikaci, která vás vyzve k zadání vaše jméno a potom zobrazí společně s datum a čas. Tady je jak:

1. Pokud již není otevřený, otevřete váš *WhatIsYourName* projektu.

2. Zadejte následující kód jazyka Visual Basic ihned po levá hranatá závorka, která následuje `Sub Main(args As String())` řádku a před `End Sub` řádku:

     ```vb
     Console.WriteLine(vbCrLf + "What is your name? ")
     Dim name = Console.ReadLine()
     Dim currentDate = DateTime.Now
     Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}")
     Console.Write(vbCrLf + "Press any key to exit... ")
     Console.ReadKey(True)
    ```

    Tento kód nahradí existující <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, a <xref:System.Console.ReadKey%2A> příkazy.

 ![Okno kódu zobrazuje co je název vašeho kódu](../ide/media/vb-codewindow-what-name.png)

3. Když se otevře v okně konzoly, zadejte název. Vaše okna konzoly by měl vypadat podobně jako na následujícím snímku obrazovky:

   ![Zobrazuje, jaké je vaše jméno, datum a čas okně konzoly a stisknutím libovolné klávesy pokračujte zpráv](../ide/media/vb-console-what-name.png)

5. Stisknutím libovolné klávesy zavřete okno konzoly.

## <a name="create-a-calculate-this-application"></a>Vytvořit aplikaci "Vypočítat to"
1. Otevřete Visual Studio 2017 a potom vyberte z panelu horní nabídce **soubor** > **nový** > **projektu...** .

2. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka Visual Basic**a potom zvolte **.NET Core**. V prostředním podokně vyberte **konzolové aplikace (.NET Core)**. Potom zadejte název souboru *CalculateThis*.  

3. Zadejte následující kód mezi `Module Program` řádku a `End Module` řádku:

   ```vb
   Public num1 As Integer
   Public num2 As Integer
   Public answer As Integer
   Sub Main()
       Console.WriteLine("Type a number and press Enter")
       num1 = Console.ReadLine()
       Console.WriteLine("Type another number to add to it and press Enter")
       num2 = Console.ReadLine()
       answer = num1 + num2
       Console.WriteLine("The answer is " & answer)
       Console.ReadLine()
   End Sub
   ```

  Okno váš kód by měl vypadat jako na následujícím snímku obrazovky:

   ![Okno kódu zobrazuje Calculate tento kód](../ide/media/vb-codewindow-calculate-this.png)

4. Klikněte na tlačítko **CalculateThis** váš program spustit. Vaše okna konzoly by měl vypadat podobně jako na následujícím snímku obrazovky:       

    ![Okno konzoly zobrazující CaluculateThis aplikaci, která zahrnuje dotazování na jaké akce lze provést.](../ide/media/vb-console-calculate-this.png)

## <a name="next-steps"></a>Další kroky
Blahopřejeme k dokončení tohoto kurzu! Další i informace o jazyka Visual Basic a Visual Studio IDE, najdete na následujících stránkách.

* [Průvodce jazykem Visual Basic](/dotnet/visual-basic/index)
* [Co je nového v jazyce Visual Basic](/dotnet/visual-basic/getting-started/whats-new)
* [IntelliSense pro soubory s kódem jazyka Visual Basic](visual-basic-specific-intellisense.md)
* [Referenční dokumentace jazyka Visual Basic](/dotnet/visual-basic/language-reference/index)
* [Základy jazyka Visual Basic pro začátečníky absolutní](https://mva.microsoft.com/en-us/training-courses/visual-basic-fundamentals-for-absolute-beginners-16507) video kurzu

---
title: Začínáme s jazykem Visual Basic v sadě Visual Studio
titleSuffix: ''
description: Zjistěte, jak vytvořit konzolové aplikace jazyka Visual Basic v sadě Visual Studio, krok za krokem.
ms.date: 08/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.custom: seodec18
ms.topic: tutorial
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 3d0f26c988b374259285af730b0f2fb9cf5f8e65
ms.sourcegitcommit: 0cdd8e8a53fb4fd5e869f07c35204419fa12783d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/10/2018
ms.locfileid: "53159578"
---
# <a name="tutorial-get-started-with-visual-basic-in-visual-studio"></a>Kurz: Začínáme s jazykem Visual Basic v sadě Visual Studio

V tomto kurzu pro Visual Basic (VB) budete používat k vytváření a spouštění aplikací pro několik různých konzoly a prozkoumat některé funkce služby Visual Studio [sady Visual Studio integrované vývojové prostředí (IDE)](../get-started/visual-studio-ide.md) při uděláte.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříme aplikaci projektu jazyka Visual Basic. Typ projektu obsahuje všechny soubory šablon, které potřebujete, než jste přidali ještě nic!

1. Otevřete Visual Studio 2017.

2. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

3. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka Visual Basic**a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **Konzolová aplikace (.NET Core)**. Potom zadejte název souboru *HelloWorld*.

   ![Konzole šablonu projektu aplikace (.NET Core) v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](../ide/media/new-project-vb-dotnetcore-whatisyourname-console-app.png)

### <a name="add-a-workgroup-optional"></a>Přidat do pracovní skupiny (nepovinné)

Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony projektu, můžete ho získat tak, že přidáte **vývoj pro různé platformy .NET Core** pracovního vytížení. Přidejte tuto úlohu v jednom z následujících způsobů, v závislosti na tom, které jsou na vašem počítači nainstalovaná aktualizace sady Visual Studio 2017.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Možnost 1: Pomocí dialogového okna Nový projekt

1. Klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Klikněte na odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/vs-open-visual-studio-installer-generic.png)

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

   ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../ide/media/quickstart-aspnet-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>Možnost 2: Pomocí nabídky panelu nástrojů

1. Zrušit z celkového počtu **nový projekt** dialogového okna a v horní nabídce vyberte **nástroje** > **stažení nástrojů a funkcí**.

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

## <a name="create-a-what-is-your-name-application"></a>Vytvoření aplikace typu "Co je vaše jméno"

Vytvoříme aplikaci, která vás vyzve k zadání vaše jméno a pak jej zobrazí datum a čas. Tady je způsob:

1. Pokud ho ještě není otevřený, otevřete vaši *WhatIsYourName* projektu.

1. Zadejte následující kód jazyka Visual Basic ihned po levá hranatá závorka, která následuje `Sub Main(args As String())` řádku a před `End Sub` řádku:

     ```vb
     Console.WriteLine(vbCrLf + "What is your name? ")
     Dim name = Console.ReadLine()
     Dim currentDate = DateTime.Now
     Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}")
     Console.Write(vbCrLf + "Press any key to exit... ")
     Console.ReadKey(True)
    ```

    Tento kód nahradí stávající <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, a <xref:System.Console.ReadKey%2A> příkazy.

   ![Co je vaše jméno kódem okno kódu](../ide/media/vb-codewindow-what-name.png)

1. Když se v okně konzoly se otevře, zadejte své jméno. Okna konzoly by měla vypadat podobně jako na následujícím snímku obrazovky:

   ![Konzole okno co je vaše jméno, času a data a stisknutím libovolné klávesy pokračovat zprávy](../ide/media/vb-console-what-name.png)

1. Stisknutím jakékoli klávesy zavřete okno konzoly.

## <a name="create-a-calculate-this-application"></a>Vytvořit aplikaci "Vypočítat to"

1. Otevřít Visual Studio 2017 a v horní nabídce vyberte příkaz **souboru** > **nový** > **projektu**.

1. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka Visual Basic**a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **Konzolová aplikace (.NET Core)**. Potom zadejte název souboru *CalculateThis*.

1. Zadejte následující kód mezi `Module Program` řádku a `End Module` řádku:

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

   ![Okno kódu znázorňující Calculate tento kód](../ide/media/vb-codewindow-calculate-this.png)

1. Klikněte na tlačítko **CalculateThis** ke spuštění programu. Okna konzoly by měla vypadat podobně jako na následujícím snímku obrazovky:

    ![Okna konzoly zobrazuje CaluculateThis aplikaci, která zahrnuje dotazování na akce, které se má provést.](../ide/media/vb-console-calculate-this.png)

## <a name="quick-answers-faq"></a>Rychlé odpovědi – nejčastější dotazy

Tady je rychlý – nejčastější dotazy ke zvýraznění některých klíčových koncepcí.

### <a name="what-is-visual-basic"></a>Co je Visual Basic?

Visual Basic je programovací jazyk zajišťující bezpečnost typů, která je navržena jako snadno učí. Je odvozen z BASIC, což znamená, že "Pro začátečníky univerzální symbolických instrukcí kód".

### <a name="what-is-visual-studio"></a>Co je sada Visual Studio?

Visual Studio je integrované vývojové sady nástrojů podporujících produktivitu pro vývojáře. Si ho představit jako program, který můžete použít k vytvoření aplikací a aplikací.

### <a name="what-is-a-console-app"></a>Co je konzolová aplikace?

Konzolová aplikace přijímá vstupní a zobrazí výstup v okně příkazového řádku, označovaný také jako do konzoly.

### <a name="what-is-net-core"></a>Co je .NET Core?

.NET core je dalším krokem evoluční rozhraní .NET Framework. Pokud rozhraní .NET Framework umožňují sdílení kódu napříč programovacími jazyky, .NET Core přidává možnost sdílení kódu napříč platformami. Ještě lepší je open source. (Rozhraní .NET Framework a .NET Core zahrnují knihovny předem připravených funkce, jakož i common language runtime (CLR), který se chová jako virtuální počítač, ve kterém se spustí váš kód.)

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto kurzu! Další ještě víc, najdete v následujícím kurzu.

> [!div class="nextstepaction"]
> [Výukové video: Základy jazyka Visual Basic pro naprosté začátečníky](https://mva.microsoft.com/en-us/training-courses/visual-basic-fundamentals-for-absolute-beginners-16507)

## <a name="see-also"></a>Viz také:

* [Co je nového v jazyce Visual Basic](/dotnet/visual-basic/getting-started/whats-new)
* [Technologie IntelliSense pro soubory kódu jazyka Visual Basic](visual-basic-specific-intellisense.md)
* [Referenční dokumentace jazyka Visual Basic](/dotnet/visual-basic/language-reference/index)
---
title: 'Kurz: Začínáme s jazykem Visual Basic'
description: Zjistěte, jak vytvořit konzolové aplikace jazyka Visual Basic v sadě Visual Studio, krok za krokem.
ms.custom: seodec18, get-started
ms.date: 03/23/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: tutorial
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: ee6866e2f40f70e2f804dc9b61b0db21c213232f
ms.sourcegitcommit: 489aca71046fb6e4aafd0a4509cd7dc149d707b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58416159"
---
# <a name="tutorial-get-started-with-visual-basic-in-visual-studio"></a>Kurz: Začínáme s jazykem Visual Basic v sadě Visual Studio

V tomto kurzu pro Visual Basic (VB) budete používat k vytváření a spouštění aplikací pro několik různých konzoly a prozkoumat některé funkce služby Visual Studio [sady Visual Studio integrované vývojové prostředí (IDE)](visual-studio-ide.md) při uděláte.

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+rc) stránku a nainstalovat zdarma.

::: moniker-end

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříme aplikaci projektu jazyka Visual Basic. Typ projektu obsahuje všechny soubory šablon, které potřebujete, než jste přidali ještě nic!

::: moniker range="vs-2017"

1. Otevřete Visual Studio 2017.

2. V horní nabídce zvolte **souboru** > **nový** > **projektu**.

3. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka Visual Basic**a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **Konzolová aplikace (.NET Core)**. Potom zadejte název souboru *HelloWorld*.

   ![Konzole šablonu projektu aplikace (.NET Core) v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](media/new-project-vb-dotnetcore-whatisyourname-console-app.png)

### <a name="add-a-workload-optional"></a>Přidat úlohu (volitelné)

Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony projektu, můžete ho získat tak, že přidáte **vývoj pro různé platformy .NET Core** pracovního vytížení. Přidejte tuto úlohu v jednom z následujících způsobů, v závislosti na tom, které jsou na vašem počítači nainstalovaná aktualizace sady Visual Studio 2017.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Option 1: Pomocí dialogového okna Nový projekt

1. Klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Klikněte na odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](../media/vs-open-visual-studio-installer-generic.png)

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

   ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../media/tutorial-aspnet-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>Option 2: Pomocí nabídky panelu nástrojů

1. Zrušit z celkového počtu **nový projekt** dialogového okna a v horní nabídce vyberte **nástroje** > **stažení nástrojů a funkcí**.

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro různé platformy .NET Core** úlohy a klikněte na tlačítko **změnit**.

::: moniker-end

::: moniker range="vs-2019"

> [!NOTE]
> Některé snímky obrazovky v tomto kurzu používají tmavý motiv. Pokud nepoužíváte tmavý motiv, ale chtěli, najdete v článku [přizpůsobit IDE sady Visual Studio a Editor](../../ide/quickstart-personalize-the-ide.md) stránku a zjistěte, jak.

1. Open Visual Studio 2019.

1. V okně start zvolte **vytvořte nový projekt**.

   ![Zobrazit okno 'vytvořte nový projekt.](../../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Na **vytvořte nový projekt** okno, zadejte nebo zadejte *konzoly* do vyhledávacího pole. Dále zvolte **jazyka Visual Basic** od jazyka seznamu a klikněte na tlačítko **Windows** ze seznamu platformy. 

   Po použití filtrů jazyka a libovolné platformy, zvolte **Konzolová aplikace (.NET Core)** šablony a klikněte na tlačítko **Další**.

   ![Výběr šablony jazyka Visual Basic pro aplikace konzoly (.NET Framework)](./media/vs-2019/vb-create-new-project-search-console-net-core-filtered.png)

   > [!NOTE]
   > Pokud se nezobrazí **Konzolová aplikace (.NET Core)** šablony, můžete jej nainstalovat z **vytvořte nový projekt** okna. V **nenašli, co hledáte?** zprávu, zvolte **nainstalovat další nástroje a funkce** odkaz.
   >
   > ![Odkaz "Nainstalovat další nástroje a funkce" z 'Nemůžete najít, co hledáte' zprávy v okně "vytvořit nový projekt.](../../get-started/media/vs-2019/not-finding-what-looking-for.png) 
   > 
   > Pak ve Visual Studio Installer, zvolte **vývoj pro různé platformy .NET Core** pracovního vytížení.
   >
   > ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../../get-started/media/dot-net-core-xplat-dev-workload.png)
   >
   > Po tomto, zvolte **změnit** tlačítko v instalačním programu sady Visual Studio. Můžete být vyzváni k uložte svou práci; Pokud ano, udělejte to. Dále zvolte **pokračovat** instalace zatížení. Pak se vraťte ke kroku 2 v tomto "[vytvořte projekt](#create-a-project)" postup.

1. V **konfigurovat nový projekt** okno, zadejte nebo vložte *WhatIsYourName* v **název projektu** pole. Potom kliknutím na možnost **vytvořit**.

   ![v okně 'Konfigurovat nový projekt' pojmenujte svůj projekt "WhatIsYourName.](./media/vs-2019/vb-name-your-project.-whatname.png)

   Visual Studio otevře nový projekt.

::: moniker-end

## <a name="create-a-what-is-your-name-application"></a>Vytvoření aplikace typu "Co je vaše jméno"

Vytvoříme aplikaci, která vás vyzve k zadání vaše jméno a pak jej zobrazí datum a čas. Tady je způsob:

 ::: moniker range="vs-2017"

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

   ![Co je vaše jméno kódem okno kódu](./media/vs-2019/vb-codewindow-what-name-dark.png)

1. Když se v okně konzoly se otevře, zadejte své jméno. Okna konzoly by měla vypadat podobně jako na následujícím snímku obrazovky:

   ![Konzole okno co je vaše jméno, času a data a stisknutím libovolné klávesy pokračovat zprávy](media/vb-console-what-name.png)

1. Stisknutím jakékoli klávesy zavřete okno konzoly.

::: moniker-end

::: moniker range="vs-2019"

1. V *WhatIsYourName* projektu, zadejte následující kód jazyka Visual Basic ihned po levá hranatá závorka, která následuje `Sub Main(args As String())` řádku a před `End Sub` řádku:

     ```vb
     Console.WriteLine(vbCrLf + "What is your name? ")
     Dim name = Console.ReadLine()
     Dim currentDate = DateTime.Now
     Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}")
     Console.Write(vbCrLf + "Press any key to exit... ")
     Console.ReadKey(True)
    ```

    Tento kód nahradí stávající <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, a <xref:System.Console.ReadKey%2A> příkazy.

   ![Co je vaše jméno kódem okno kódu](./media/vs-2019/vb-codewindow-what-name-dark.png)

1. Když se v okně konzoly se otevře, zadejte své jméno. Okna konzoly by měla vypadat podobně jako na následujícím snímku obrazovky:

   ![Konzole okno co je vaše jméno, času a data a stisknutím libovolné klávesy pokračovat zprávy](media/vb-console-what-name.png)

1. Stisknutím jakékoli klávesy zavřete okno konzoly.

 ::: moniker-end

## <a name="create-a-calculate-this-application"></a>Vytvořit aplikaci "Vypočítat to"

::: moniker range="vs-2017"

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

   ![Okno kódu CalculateThis kódem](media/vb-codewindow-calculate-this.png)

1. Klikněte na tlačítko **CalculateThis** ke spuštění programu. Okna konzoly by měla vypadat podobně jako na následujícím snímku obrazovky:

    ![Okna konzoly zobrazuje CalculateThis aplikaci, která zahrnuje dotazování na akce, které se má provést.](media/vb-console-calculate-this.png)

::: moniker-end 

::: moniker range="vs-2019"

1. V okně start zvolte **vytvořte nový projekt**. 

1. Na **vytvořte nový projekt** okno, zadejte nebo zadejte *konzoly* do vyhledávacího pole. Dále zvolte **jazyka Visual Basic** od jazyka seznamu a klikněte na tlačítko **Windows** ze seznamu platformy. 

1. Po použití filtrů jazyka a libovolné platformy, zvolte **Konzolová aplikace (.NET Core)** šablony a klikněte na tlačítko **Další**.

   Potom v **konfigurovat nový projekt** okno, zadejte nebo vložte *WhatIsYourName* v **název projektu** pole. Dále zvolte **vytvořit**.

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

   ![Okno kódu CalculateThis kódem](media/vb-codewindow-calculate-this.png)

1. Klikněte na tlačítko **CalculateThis** ke spuštění programu. Okna konzoly by měla vypadat podobně jako na následujícím snímku obrazovky:

    ![Okna konzoly zobrazuje CalculateThis aplikaci, která zahrnuje dotazování na akce, které se má provést.](media/vb-console-calculate-this.png)

::: moniker-end

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
> [Vytvoření knihovny pomocí jazyka Visual Basic a .NET Core SDK v sadě Visual Studio](/dotnet/core/tutorials/vb-library-with-visual-studio)

## <a name="see-also"></a>Viz také:

* [Návody pro jazyk Visual Basic](/dotnet/visual-basic/walkthroughs)
* [Referenční dokumentace jazyka Visual Basic](/dotnet/visual-basic/language-reference/index)
* [Technologie IntelliSense pro soubory kódu jazyka Visual Basic](../../ide/visual-basic-specific-intellisense.md)

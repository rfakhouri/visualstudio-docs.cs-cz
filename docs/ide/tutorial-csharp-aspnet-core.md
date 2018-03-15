---
title: "Začínáme s C# a ASP.NET Core v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 12/11/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 9a24ccbcecc2d5bd4d5799ada048fee0004514f7
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="getting-started-with-c-and-aspnet-in-visual-studio"></a>Začínáme s C# a ASP.NET v sadě Visual Studio
V tomto kurzu pro vývoj C# pomocí ASP.NET Core pomocí sady Visual Studio budete vytvořit webovou aplikaci ASP.NET Core C#, přidejte do ní kód, prozkoumejte některé funkce integrovaného vývojového prostředí a spuštění aplikace.

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky instalaci zdarma.

## <a name="before-you-begin"></a>Než začnete
Zde je rychlý nejčastější dotazy k vám představí některé klíčové koncepty.
### <a name="what-is-c"></a>Co je C#?
[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) je bezpečnost typů a objektově orientované programovací jazyk, který je navržená tak, aby robustní a snadno Další.
### <a name="what-is-aspnet-core"></a>Co je ASP.NET Core?
ASP.NET Core je představuje open source a napříč platformami rozhraní pro vytváření aplikací připojené k Internetu, jako třeba webové aplikace a služby. Aplikace ASP.NET Core můžete spustit v rozhraní .NET Framework nebo .NET Core. Můžete vyvíjet a spuštění aplikace a platformy ASP.NET Core v systému Windows, Mac a Linux. ASP.NET Core je open source v [Githubu](https://github.com/aspnet/home).
### <a name="what-is-visual-studio"></a>Co je Visual Studio?
Visual Studio je sada integrované vývojové kancelářské nástroje pro vývojáře. Považujte ho za programu, které můžete použít k vytvoření programy a aplikace.  

## <a name="start-developing"></a>Začít vyvíjet
Jste připravení začít vyvíjet? Jdeme!

### <a name="create-a-project"></a>Vytvoření projektu
Nejdřív vytvoříte projekt ASP.NET Core. Typ projektu se dodává s všechny soubory šablony, které budete potřebovat, než jste přidali i nic.

1. Open Visual Studio 2017.

2. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .

3. V **nový projekt** dialogové okno v levém podokně rozbalte **Visual C#**, rozbalte položku **webové**a potom zvolte **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**, název souboru *MyCoreApp*a potom zvolte **OK**.   

   ![Šablona projektu webové aplikace ASP.NET Core v dialogovém okně Nový projekt v prostředí Visual Studio IDE](../ide/media/new-project-csharp-aspnet-mycoreapp.png)

#### <a name="add-a-workload-optional"></a>Přidat úloha (volitelné)
Pokud nevidíte **webové aplikace ASP.NET Core** šablony projektu, můžete ho získat tak, že přidáte **ASP.NET a webové vývoj** zatížení. Můžete přidat tímto zatížením v jednom z následujících způsobů, v závislosti na tom, které instalují aktualizace Visual Studio 2017 na váš počítač.

##### <a name="option-1-use-the-new-project-dialog-box"></a>Možnost 1: Pomocí dialogového okna Nový projekt
1. Klikněte **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

  ![Klikněte na odkaz otevřete instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/vs-open-visual-studio-installer-generic.png)

2. Spustí instalační program Visual Studio. Vyberte **ASP.NET a webové vývoj** zatížení a potom zvolte **upravit**.

   ![Vývoj pro různé platformy zatížení .NET core v instalačním programu Visual Studio](../ide/media/asp-dot-net-web-dev-workload.png)

##### <a name="option-2-use-the-tools-menu-bar"></a>Možnost 2: Pomocí nabídky panelu nástrojů
1. Zrušit mimo **nový projekt** dialogové okno a z panelu horní nabídce zvolte **nástroje** > **funkcí a nástrojů pro získání...** .

2. Spustí instalační program Visual Studio. Vyberte **ASP.NET a webové vývoj** zatížení a potom zvolte **upravit**.   

#### <a name="add-a-project-template"></a>Přidání šablony projektu
1. V **nové webové aplikace ASP.NET Core** dialogovém okně vyberte **webové aplikace (Model-View-Controller)** šablona projektu.  

2. Vyberte **technologii ASP.NET 2.0 základní** v hlavní nabídce rozevíracího seznamu. (Pokud nevidíte **technologii ASP.NET 2.0 základní** v seznamu, nainstalujte ji podle **Stáhnout** odkaz, který by se měla objevit v žlutý pruh v horní části dialogové okno.) Zvolte **OK**.

   ![Dialogové okno nové webové aplikace ASP.NET Core](../ide/media/new-project-csharp-aspnet-web-app-mvc.png)

### <a name="about-your-solution"></a>O řešení
Toto řešení zahrnuje vzor architektury Model-View-Controller (MVC), který odděluje aplikace do tří hlavních součástí:

* **Modely** zahrnují třídy, které představují data aplikace. Vynutit obchodní pravidla pro tato data pomocí tříd modelu logiku ověření. Model objektů obvykle načíst a ukládají stav modelu v databázi.
* **Zobrazení** jsou komponenty, které zobrazí aplikace uživatelské rozhraní (UI). Obecně platí toto uživatelské rozhraní zobrazí data modelu.
* **Řadiče** zahrnují třídy, které zpracovávají požadavky prohlížeče. Načítají data modelu a volání Zobrazit šablony, které vrátí odpověď. V aplikaci MVC zobrazení zobrazí jenom informace; kontroler zpracovává a reaguje na vstup uživatele a interakce.

Vzor MVC pomáhá vytvářet aplikace, které se snadněji testování a aktualizace než tradiční monolitický aplikace.

### <a name="tour-your-solution"></a>Prohlídka řešení
1. Šablona projektu vytvoří řešení s jednu s názvem projektu ASP.NET Core **MyCoreApp**. Rozbalte uzel projektu zobrazit její obsah.

    ![Průzkumník řešení technologie ASP.NET v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-mycoreapp.png)

1. Otevřete **HomeController.cs** souboru z **řadiče** složky.

      ![HomeController.cs soubor v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

2. Zobrazení **HomeController.cs**

  ![HomeController.cs v okně kódu aplikace Visual Studio](../ide/media/csharp-aspnet-home-controller-code.png)

4. Projekt má také **zobrazení** složky, která obsahuje jiné složky, které jsou mapovány na každém řadiči (a jeden pro **sdílené** zobrazení). Například v zobrazení CSHTML souboru (rozšíření HTML) **/domácí/o** cesta by byla v **Views/Home/About.cshtml**. Umožňuje otevřete tento soubor.

  ![About.cshtml soubor v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

5. Tento soubor CSHTML používá syntaxi Razor k vykreslení HTML založené na kombinaci standardní značky a vložené C#.

  ![About.cshtml v okně kódu aplikace Visual Studio](../ide/media/csharp-aspnet-about-cshtml-code.png)

 >[!NOTE]
 > Další informace o tom najdete v tématu [Začínáme s C# a technologii ASP.NET pomocí syntaxe Razor](/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c) stránky.

6. Řešení obsahuje také **wwwroot** složky, která je kořenový adresář pro svůj web. Statické lokality obsah, například šablon stylů CSS, Image a knihoven jazyka JavaScript, můžete vložit přímo na cesty chcete by mohly být při nasazení webu.

 ![Wwwroot složky v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-wwwroot.png)

7. Existují také celou řadu konfiguračních souborů, které slouží ke správě projektu, jeho balíčky a aplikace za běhu. Například výchozí aplikace [konfigurace](/aspnet/core/fundamentals/configuration) je uložen v **appSettings.JSON určený**. Však můžete přepsat některé nebo všechny z těchto nastavení na základě na prostředí, například tím, že poskytuje **appsettings. Development.JSON** souboru **vývoj** prostředí.

 ![Konfigurační soubory v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-config-files.png)

## <a name="run-and-debug-the-application"></a>Spuštění a ladění aplikace

1. Vyberte **IIS Express** tlačítko v integrovaném vývojovém prostředí pro sestavení a spuštění aplikace v režimu ladění. (Nebo stisknout **F5**, nebo zvolte **ladění > Spustit ladění** z řádku nabídek.)

  ![Klikněte na tlačítko IIS Express v sadě Visual Studio](../ide/media/csharp-aspnet-iis-express-button.png)

  > [!NOTE]
  > Pokud se zobrazí chybová zpráva, která uvádí, že **nebylo možné se připojit k webovému serveru služby IIS Express**, zavřete Visual Studio a otevřete jej pomocí **spustit jako správce** možnost v nabídce klikněte pravým tlačítkem nebo kontextu. Pak spusťte aplikaci znovu.

1. Visual Studio otevře okno prohlížeče. Vyberte **o**.

 ![Vyberte o v okně prohlížeče pro vaši aplikaci.](../ide/media/csharp-aspnet-browser-page.png)

 Kromě jiných věcí vykreslí stránku v prohlížeči o text, který je nastaveno v souboru HomeController.cs.

   ![Zobrazit text na stránce o](../ide/media/csharp-aspnet-browser-page-about.png)

1. Zachovat okna prohlížeče otevřete a zpět k sadě Visual Studio. Otevřete **Controllers/HomeController.cs** Pokud ještě není otevřené.

 ![Otevřete soubor HomeController.cs v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

1. Nastavte zarážky v prvním řádku **o** metoda. To provedete kliknutím na okraj nebo nastavte kurzor na řádku a stiskněte klávesu **F9**.

  Tento řádek nastaví některá data **ViewData** kolekce, který je vykreslen na stránce CSHTML v **Views/Home/About.cshtml**.

 ![V první řádek metody o v About.cshtml nastavte zarážky.  ](../ide/media/csharp-aspnet-home-controller-code-set-breakpoint.png)

1. Vraťte se do prohlížeče a aktualizujte stránku. O. Tím se aktivuje zarážek v sadě Visual Studio.

1. V sadě Visual Studio, umístění ukazatele myši **ViewData** člen, pokud chcete zobrazit data.

 ![Zobrazení člen ViewData metody. O další informace získáte](../ide/media/csharp-aspnet-home-controller-view-breakpoint-info.png)

1. Odeberte zarážek aplikace pomocí stejného postupu, které jste použili ho přidejte.

1. Otevřete **Views/Home/About.cshtml**.

 ![Vyberte About.cshtml v Průzkumníku řešení](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

1. Změňte text **"Další"** k **"změnit"** a soubor uložte.

 ![Změna textu, který čte "Další" na text, který čte "změnit"](../ide/media/csharp-aspnet-about-cshtml-code-change.png)

1. Vraťte se k okno prohlížeče a zobrazit aktualizovaný text. (Pokud nevidíte text, který jste změnili, aktualizujte stránku prohlížeče.)

  ![Aktualizujte okno prohlížeče a zobrazit změněného textu](../ide/media/csharp-aspnet-browser-page-about-changed.png)

1. Vyberte **Zastavte ladění** tlačítka panelu nástrojů na Zastavte ladění. (Nebo stisknout **Shift**+**F5**, nebo zvolte **ladění** > **Zastavte ladění** z řádku nabídek.)

 ![Klikněte na tlačítko Zastavit ladění na panelu nástrojů](../ide/media/csharp-aspnet-stop-debugging.png)

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto kurzu! Věříme, že jste se dozvěděli, chvíli o C#, ASP.NET Core a Visual Studio IDE. I více informací naleznete v následujícím kurzu pokračujte.

 > [!div class="nextstepaction"]
 > [Začínáme s ASP.NET MVC jádra a sady Visual Studio](/aspnet/core/tutorials/first-mvc-app/start-mvc?tabs=aspnetcore2x)

---
title: Začínáme s C# a ASP.NET Core v sadě Visual Studio
ms.custom: ''
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 9df1cbae3b0233a8711ab6a287513d89670df4d4
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39177367"
---
# <a name="get-started-with-c-and-aspnet-in-visual-studio"></a>Začínáme s C# a technologie ASP.NET v sadě Visual Studio

V tomto kurzu o vývoji C# s využitím ASP.NET Core pomocí sady Visual Studio budete vytvoření webové aplikace v C# ASP.NET Core, přidejte do ní kód, prozkoumat některé funkce integrovaného vývojového prostředí a spuštění aplikace.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="before-you-begin"></a>Než začnete

Tady je rychlý – nejčastější dotazy vám představí některé klíčové koncepty.

### <a name="what-is-c"></a>Co je C#?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) je typově bezpečný a objektově orientovaný programovací jazyk, který bude robustní a snadno osvojitelná.

### <a name="what-is-aspnet-core"></a>Co je ASP.NET Core?

ASP.NET Core je open source a multiplatformní rozhraní pro vytváření aplikací připojených k Internetu, jako jsou webové aplikace a služby. Aplikace ASP.NET Core můžete spustit na .NET Core nebo .NET Framework. Můžete vyvíjet a spouštět multiplatformní aplikace ASP.NET Core ve Windows, Mac a Linux. ASP.NET Core je open source v [Githubu](https://github.com/aspnet/home).

### <a name="what-is-visual-studio"></a>Co je sada Visual Studio?

Visual Studio je integrované vývojové sady nástrojů podporujících produktivitu pro vývojáře. Si ho představit jako program, který můžete použít k vytvoření aplikací a aplikací.

## <a name="start-developing"></a>Začít s vývojem

Jste připravení začít s vývojem? Jdeme!

### <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt ASP.NET Core. Typ projektu obsahuje všechny soubory šablon, které potřebujete, než jste přidali ještě něco.

1. Otevřete Visual Studio 2017.

2. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

3. V **nový projekt** dialogové okno v levém podokně rozbalte **Visual C#**, rozbalte **webové**a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**, pojmenujte soubor *MyCoreApp*a klikněte na tlačítko **OK**.

   ![Šablona projektu webové aplikace ASP.NET Core v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](../ide/media/new-project-csharp-aspnet-mycoreapp.png)

#### <a name="add-a-workload-optional"></a>Přidat úlohu (volitelné)

Pokud se nezobrazí **webové aplikace ASP.NET Core** šablony projektu, můžete ho získat tak, že přidáte **vývoj pro ASP.NET a web** pracovního vytížení. Přidejte tuto úlohu v jednom z následujících způsobů, v závislosti na tom, které jsou na vašem počítači nainstalovaná aktualizace sady Visual Studio 2017.

##### <a name="option-1-use-the-new-project-dialog-box"></a>Možnost 1: Pomocí dialogového okna Nový projekt

1. Vyberte **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Vyberte odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/vs-open-visual-studio-installer-generic.png)

2. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.

   ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../ide/media/asp-dot-net-web-dev-workload.png)

##### <a name="option-2-use-the-tools-menu-bar"></a>Možnost 2: Použití nabídky panelu nástrojů

1. Zrušit z celkového počtu **nový projekt** dialogového okna a v horní nabídce vyberte **nástroje** > **stažení nástrojů a funkcí**.

2. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.

#### <a name="add-a-project-template"></a>Přidat šablonu projektu

1. V **nová webová aplikace ASP.NET Core** dialogového okna zvolte **webové aplikace (Model-View-Controller)** šablony projektu.

2. Vyberte **ASP.NET Core 2.0** z hlavní nabídky rozevíracího seznamu. (Pokud se nezobrazí **ASP.NET Core 2.0** v seznamu, nainstalujte ji pomocí následujících **Stáhnout** odkaz, který by se měla objevit v žlutý pruh v horní části dialogu.) Zvolte **OK**.

   ![Dialogové okno nové webové aplikace ASP.NET Core](../ide/media/new-project-csharp-aspnet-web-app-mvc.png)

### <a name="about-your-solution"></a>Informace o řešení

Toto řešení má následující formát, Model-View-Controller (MVC) architektury, která odděluje aplikace do tří hlavních součástí:

* **Modely** zahrnují třídy, které představují data aplikace. Tříd modelu pomocí logiku ověřování k vynucení obchodní pravidla pro tato data. Objekty modelu obvykle, načíst a ukládají stav modelu v databázi.
* **Zobrazení** jsou komponenty, které zobrazují aplikace uživatelského rozhraní (UI). Obecně platí toto uživatelské rozhraní zobrazí data modelu.
* **Kontrolery** zahrnují třídy, které zpracovávají požadavky prohlížeče. Načítají data modelu a volání Zobrazit šablony, které vrátí odpověď. V aplikaci MVC zobrazení se zobrazí pouze informace; kontroler zpracovává a reaguje na vstup uživatele a interakce.

Vzor MVC pomáhá vytvářet aplikace, které usnadňuje testování a aktualizace než tradiční monolitické aplikace.

### <a name="tour-your-solution"></a>Prohlédnete si vašich řešení

 1. Šablona projektu vytvoří řešení pomocí jednoho projektu ASP.NET Core, který je pojmenován **MyCoreApp**. Rozbalte uzel projektu k vystavení jeho obsah.

    ![Průzkumník řešení technologie ASP.NET v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-mycoreapp.png)

 2. Otevřít *HomeController.cs* soubor **řadiče** složky.

     ![HomeController.cs souboru v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

 3. Zobrazení *HomeController.cs*

     ![HomeController.cs v okně kódu sady Visual Studio](../ide/media/csharp-aspnet-home-controller-code.png)

 4. Projekt má také **zobrazení** složku, která obsahuje další složky, které mapují na každém řadiči (a jeden pro **Shared** zobrazení). Například v zobrazení CSHTML souboru (rozšíření HTML) */Home/About* cesta bude na *Views/Home/About.cshtml*. Otevřete tento soubor.

     ![About.cshtml souboru v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

 5. Tento soubor CSHTML používá syntaxi Razor k vykreslení HTML na základě kombinace standardních značek a vložené C#.

     ![About.cshtml v okně kódu sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-code.png)

   >[!NOTE]
   > Další informace o to, najdete v článku [Začínáme s C# a technologii ASP.NET pomocí syntaxe Razor](/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c) stránky.

 6. Řešení obsahuje také *wwwroot* složku, která je kořenový adresář pro váš web. Statické webový obsah, jako jsou šablony stylů CSS, obrázky a knihoven jazyka JavaScript, můžete vložit přímo na cesty byste jim být při nasazení webu.

     ![složky Wwwroot v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-wwwroot.png)

 7. Existují také celou řadu konfiguračních souborů, které slouží ke správě projektu, jeho balíčky a aplikace za běhu. Například výchozí aplikaci [konfigurace](/aspnet/core/fundamentals/configuration) je uložen v *appsettings.json*. Však můžete přepsat všech nebo některých z těchto nastavení na základě na prostředí, například tím, že poskytuje *appsettings. Development.JSON* souboru **vývoj** prostředí.

     ![Konfigurační soubory v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-config-files.png)

## <a name="run-and-debug-the-application"></a>Spuštění a ladění aplikace

1. Zvolte **služby IIS Express** tlačítko v integrovaném vývojovém prostředí pro sestavení a spuštění aplikace v režimu ladění. (Nebo stisknout **F5**, nebo zvolte **ladit > Spustit ladění** z řádku nabídek.)

   ![Vyberte tlačítko služby IIS Express v sadě Visual Studio](../ide/media/csharp-aspnet-iis-express-button.png)

  > [!NOTE]
  > Pokud se zobrazí chybová zpráva s upozorněním **nelze se připojit k webovému serveru služby IIS Express**, zavřete sadu Visual Studio a otevřete jej pomocí **spustit jako správce** možnost v nabídce klikněte pravým tlačítkem nebo kontext. Spusťte aplikaci znovu.

2. Visual Studio otevře okno prohlížeče. Vyberte **o**.

   ![Vyberte o v okně prohlížeče pro vaši aplikaci](../ide/media/csharp-aspnet-browser-page.png)

 Mimo jiné **o** text, který je nastavena v vykreslí stránku v prohlížeči *HomeController.cs* souboru.

   ![Zobrazit text na stránce o](../ide/media/csharp-aspnet-browser-page-about.png)

3. Nechte okno prohlížeče otevřít a vrátí do sady Visual Studio. Otevřete *Controllers/HomeController.cs* Pokud ještě není otevřený.

   ![Otevření souboru HomeController.cs z Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

4. Nastavte zarážku v prvním řádku **o** metody. Chcete-li to provést, klikněte na okraji nebo nastavte kurzor na řádku a stisknutím klávesy **F9**.

  Tento řádek nastaví některá data **ViewData** kolekce, který je vykreslen na stránce CSHTML v *Views/Home/About.cshtml*.

   ![Nastavte zarážku na prvním řádku metody o v About.cshtml.  ](../ide/media/csharp-aspnet-home-controller-code-set-breakpoint.png)

5. Vraťte se do prohlížeče a aktualizace **o** stránky. Tím se aktivuje zarážky v sadě Visual Studio.

6. V sadě Visual Studio, najedete myší **ViewData** člen zobrazíte jeho data.

   ![Zobrazení členů ViewData metody o zobrazíte další informace](../ide/media/csharp-aspnet-home-controller-view-breakpoint-info.png)

7. Odeberte narážku aplikace stejným způsobem, který jste použili ho přidat.

8. Otevřít *Views/Home/About.cshtml*.

   ![V Průzkumníku řešení vyberte About.cshtml](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

9. Změní celý text **"Další"** k **"změnit"** a soubor uložte.

   ![Změnit text, který čte "Další" na text, který čte "změnil"](../ide/media/csharp-aspnet-about-cshtml-code-change.png)

10. Vraťte se do okna prohlížeče, zobrazí aktualizovaný text. (Pokud se nezobrazí text, který jste změnili, aktualizujte prohlížeč.)

    ![Aktualizujte okno prohlížeče a zobrazit změněný text](../ide/media/csharp-aspnet-browser-page-about-changed.png)

11. Zvolte **Zastavit ladění** tlačítko na panelu nástrojů pro zastavení ladění. (Nebo stisknout **Shift**+**F5**, nebo zvolte **ladění** > **Zastavit ladění** z řádku nabídek.)

   ![Klikněte na tlačítko Zastavit ladění na panelu nástrojů](../ide/media/csharp-aspnet-stop-debugging.png)

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto kurzu! Doufáme, že jste se dozvěděli ještě něco o jazyce C#, ASP.NET Core a integrovaném vývojovém prostředí sady Visual Studio. Pokud chcete zobrazit aplikaci spuštěnou na veřejný server, vyberte na následující tlačítko.

> [!div class="nextstepaction"]
> [Nasaďte aplikaci do služby Azure App Service](..//deployment/quickstart-deploy-to-azure.md)

Můžete také další informace o použití rozhraní framework Model-View-Controller (MVC) v ASP.NET Core v tomto kurzu, [Začínáme s ASP.NET Core MVC a sady Visual Studio](/aspnet/core/tutorials/first-mvc-app/start-mvc?tabs=aspnetcore2x).

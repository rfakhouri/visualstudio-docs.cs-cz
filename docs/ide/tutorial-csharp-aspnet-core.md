---
title: Začínáme s C# a ASP.NET Core v sadě Visual Studio
description: Zjistěte, jak vytvořit webovou aplikaci ASP.NET Core v sadě Visual Studio s C#, krok za krokem.
ms.custom: ''
ms.date: 08/10/2018
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
ms.openlocfilehash: fb1532a76d9bc530146ba5a0f563bcaa9389226c
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/13/2018
ms.locfileid: "42623987"
---
# <a name="tutorial-get-started-with-c-and-aspnet-core-in-visual-studio"></a>Kurz: Začínáme s C# a ASP.NET Core v sadě Visual Studio

V tomto kurzu o vývoji C# s využitím ASP.NET Core pomocí sady Visual Studio budete vytvoření webové aplikace v C# ASP.NET Core, provést změny, prozkoumat některé funkce integrovaného vývojového prostředí a spuštění aplikace.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt ASP.NET Core. Typ projektu obsahuje všechny soubory šablon, které potřebujete pro web, než jste přidali ještě nic!

1. Otevřete Visual Studio 2017.

2. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**. 

3. V **nový projekt** dialogové okno v levém podokně rozbalte **Visual C#**, rozbalte **webové**a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**. Pojmenujte jej *MyCoreApp* a zvolte **OK**.

   ![Šablona projektu webové aplikace ASP.NET Core v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](../ide/media/csharp-aspnet-choose-template-name-mycoreapp-mvc.png)

### <a name="add-a-workload-optional"></a>Přidat úlohu (volitelné)

Pokud se nezobrazí **webové aplikace ASP.NET Core** šablony projektu, můžete ho získat tak, že přidáte **vývoj pro ASP.NET a web** pracovního vytížení. Přidejte tuto úlohu v jednom z následujících způsobů, v závislosti na tom, které jsou na vašem počítači nainstalovaná aktualizace sady Visual Studio 2017.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Možnost 1: Pomocí dialogového okna Nový projekt

1. Vyberte **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.

   ![Vyberte odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/vs-open-visual-studio-installer-generic.png)

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.

   ![Úlohy pro vývoj pro různé platformy .NET core v instalačním programu sady Visual Studio](../ide/media/quickstart-aspnet-workload.png)

   (Může mít ukončit sadu Visual Studio, abyste mohli pokračovat v instalaci nové úlohy.)

#### <a name="option-2-use-the-tools-menu-bar"></a>Možnost 2: Použití nabídky panelu nástrojů

1. Zrušit z celkového počtu **nový projekt** dialogové okno. Potom v horní nabídce vyberte **nástroje** > **stažení nástrojů a funkcí**.

1. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.

   (Může mít ukončit sadu Visual Studio, abyste mohli pokračovat v instalaci nové úlohy.)

### <a name="add-a-project-template"></a>Přidat šablonu projektu

1. V **nová webová aplikace ASP.NET Core** dialogového okna zvolte **webové aplikace (Model-View-Controller)** šablony projektu.

1. Ověřte, že **ASP.NET Core 2.0** se zobrazí v horní nabídce rozevíracího seznamu. Potom kliknutím na možnost **OK**.

   ![Dialogové okno nové webové aplikace ASP.NET Core](../ide/media/new-project-csharp-aspnet-web-app-mvc.png)

### <a name="about-your-solution"></a>Informace o řešení

Toto řešení má následující formát, Model-View-Controller (MVC) architektury, která odděluje aplikace do tří hlavních součástí:

* **Modely** zahrnují třídy, které představují data aplikace. Tříd modelu pomocí logiku ověřování k vynucení obchodní pravidla pro tato data. Objekty modelu obvykle, načíst a ukládají stav modelu v databázi.
* **Zobrazení** jsou komponenty, které zobrazují aplikace uživatelského rozhraní (UI). Obecně platí toto uživatelské rozhraní zobrazí data modelu.
* **Kontrolery** zahrnují třídy, které zpracovávají požadavky prohlížeče. Načítají data modelu a volání Zobrazit šablony, které vrátí odpověď. V aplikaci MVC zobrazení se zobrazí pouze informace; kontroler zpracovává a reaguje na vstup uživatele a interakce.

Vzor MVC pomáhá vytvářet aplikace, které usnadňuje testování a aktualizace než tradiční monolitické aplikace.

## <a name="tour-your-solution"></a>Prohlédnete si vašich řešení

 1. Šablona projektu vytvoří řešení pomocí jednoho projektu ASP.NET Core, který je pojmenován **MyCoreApp**. Rozbalte uzel projektu k vystavení jeho obsah.

    ![Průzkumník řešení technologie ASP.NET v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-mycoreapp-mvc.png)

 1. Otevřít *HomeController.cs* soubor **řadiče** složky.

     ![HomeController.cs souboru v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

 1. Zobrazení *HomeController.cs* souboru.

     ![HomeController.cs v okně kódu sady Visual Studio](../ide/media/csharp-aspnet-home-controller-code.png)

 1. Projekt má také **zobrazení** složku, která obsahuje podsložky, které mapují na každém řadiči. Například v zobrazení CSHTML souboru (rozšíření HTML) */Home/About* cesta bude na *Views/Home/About.cshtml*. Otevřete tento soubor.

     ![About.cshtml souboru v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

    Tento soubor CSHTML používá syntaxi Razor k vykreslení HTML na základě kombinace standardních značek a vložené C#.

     ![About.cshtml v okně kódu sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-code.png)

    >[!NOTE]
    > Další informace o syntaxi Razor, najdete v článku [Začínáme s C# a technologii ASP.NET pomocí syntaxe Razor](/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c) stránky.

 1. Také obsahuje projekt **wwwroot** složku, která je kořenový adresář pro váš web. Rozbalte složky a zobrazit jeho obsah.

     ![složky Wwwroot v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-wwwroot.png)

    Můžete vložit obsah statického webu&mdash;jako jsou šablony stylů CSS, obrázky a knihovny JavaScript&mdash;přímo v cestách kamkoli chcete.

 1. Existuje několik konfiguračních souborů, které spravují projektu, jeho balíčky a aplikace za běhu. Například výchozí aplikaci [konfigurace](/aspnet/core/fundamentals/configuration) je uložen v *appsettings.json*. Tato nastavení však můžete přepsat pomocí *appsettings. Development.JSON*. Rozbalte **appsettings.json** soubor zobrazíte **appsettings. Development.JSON** souboru.

     ![Konfigurační soubory v Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-config-files.png)

## <a name="run-debug-and-make-changes"></a>Spouštět, ladit a provést změny

1. Zvolte **služby IIS Express** tlačítko v integrovaném vývojovém prostředí pro sestavení a spuštění aplikace v režimu ladění. (Nebo stisknout **F5**, nebo zvolte **ladit > Spustit ladění** z řádku nabídek.)

     ![Vyberte tlačítko služby IIS Express v sadě Visual Studio](../ide/media/csharp-aspnet-iis-express-button.png)

     > [!NOTE]
     > Pokud se zobrazí chybová zpráva s upozorněním **nelze se připojit k webovému serveru služby IIS Express**, zavřete sadu Visual Studio a otevřete jej pomocí **spustit jako správce** možnost v nabídce klikněte pravým tlačítkem nebo kontext. Spusťte aplikaci znovu.

1. Visual Studio otevře okno prohlížeče. Vyberte **o**.

   ![Vyberte o v okně prohlížeče pro vaši aplikaci](../ide/media/csharp-aspnet-browser-page.png)

   Mimo jiné **o** text, který je nastavena v vykreslí stránku v prohlížeči *HomeController.cs* souboru.

   ![Zobrazit text na stránce o](../ide/media/csharp-aspnet-browser-page-about.png)

1. Nechte okno prohlížeče otevřít a vrátí do sady Visual Studio. Otevřete *Controllers/HomeController.cs* Pokud ještě není otevřený.

   ![Otevření souboru HomeController.cs z Průzkumníku řešení v sadě Visual Studio](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

1. Nastavte zarážku v prvním řádku **o** metody. Chcete-li to provést, klikněte na okraji nebo nastavte kurzor na řádku a stisknutím klávesy **F9**.

   Tento řádek nastaví některá data **ViewData** kolekce, který je vykreslen na stránce CSHTML v *Views/Home/About.cshtml*.

   ![Nastavte zarážku na prvním řádku metody o v About.cshtml.  ](../ide/media/csharp-aspnet-home-controller-code-set-breakpoint.png)

1. Vraťte se do prohlížeče a aktualizace **o** stránky. Tím se aktivuje zarážky v sadě Visual Studio.

1. V sadě Visual Studio, najedete myší **ViewData** člen zobrazíte jeho data.

   ![Zobrazení členů ViewData metody o zobrazíte další informace](../ide/media/csharp-aspnet-home-controller-view-breakpoint-info.png)

1. Odeberte narážku aplikace stejným způsobem, který jste použili ho přidat.

1. Otevřít *Views/Home/About.cshtml*.

   ![V Průzkumníku řešení vyberte About.cshtml](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

1. Změní celý text **"Další"** k **"změnit"** a soubor uložte.

   ![Změnit text, který čte "Další" na text, který čte "změnil"](../ide/media/csharp-aspnet-about-cshtml-code-change.png)

1. Vraťte se do okna prohlížeče, zobrazí aktualizovaný text. (Pokud se nezobrazí text, který jste změnili, aktualizujte prohlížeč.)

    ![Aktualizujte okno prohlížeče a zobrazit změněný text](../ide/media/csharp-aspnet-browser-page-about-changed.png)

1. Zvolte **Zastavit ladění** tlačítko na panelu nástrojů pro zastavení ladění. (Nebo stisknout **Shift**+**F5**, nebo zvolte **ladění** > **Zastavit ladění** z řádku nabídek.)

   ![Klikněte na tlačítko Zastavit ladění na panelu nástrojů](../ide/media/csharp-aspnet-stop-debugging.png)

## <a name="quick-answers-faq"></a>Rychlé odpovědi – nejčastější dotazy

Tady je rychlý – nejčastější dotazy ke zvýraznění některých klíčových koncepcí.

### <a name="what-is-c"></a>Co je C#?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) je typově bezpečný a objektově orientovaný programovací jazyk, který bude robustní a snadno osvojitelná.

### <a name="what-is-aspnet-core"></a>Co je ASP.NET Core?

ASP.NET Core je open source a multiplatformní rozhraní pro vytváření aplikací připojených k Internetu, jako jsou webové aplikace a služby. Aplikace ASP.NET Core můžete spustit na .NET Core nebo .NET Framework. Můžete vyvíjet a spouštět multiplatformní aplikace ASP.NET Core ve Windows, Mac a Linux. ASP.NET Core je open source v [Githubu](https://github.com/aspnet/home).

### <a name="what-is-visual-studio"></a>Co je sada Visual Studio?

Visual Studio je integrované vývojové sady nástrojů podporujících produktivitu pro vývojáře. Si ho představit jako program, který můžete použít k vytvoření aplikací a aplikací.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto kurzu! Doufáme, že jste se dozvěděli ještě něco o jazyce C#, ASP.NET Core a integrovaném vývojovém prostředí sady Visual Studio. Další informace o vytváření webové aplikace nebo webu pomocí jazyka C# a technologie ASP.NET, pokračujte v následujících kurzech:

> [!div class="nextstepaction"]
> [Vytvoření webové aplikace MVC s ASP.NET Core](/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-2.1&tabs=aspnetcore2x)
>
> [!div class="nextstepaction"]
> [Vytvoření webové aplikace stránky Razor pomocí ASP.NET Core](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)

## <a name="see-also"></a>Viz také:

[Publikování webové aplikace do služby Azure App Service pomocí sady Visual Studio](..//deployment/quickstart-deploy-to-azure.md)
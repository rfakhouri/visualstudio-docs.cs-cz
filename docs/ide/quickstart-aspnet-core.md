---
title: Vytvoření webové aplikace v ASP.NET CoreC#
description: Zjistěte, jak vytvořit jednoduchou webovou aplikaci Hello World v sadě Visual Studio s C# a ASP.NET Core, krok za krokem.
ms.custom: mvc,seodec18
ms.date: 06/06/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: quickstart
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 0e701fd45230295222ffc6e17c05052e01b47189
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66745038"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Rychlý start: Vytvoření vaší první webové aplikace ASP.NET Core pomocí sady Visual Studio

V tomto úvodu 5 až 10 minut na tom, jak pomocí sady Visual Studio vytvoříte jednoduchou webovou aplikaci "Hello World" pomocí šablony projektu ASP.NET a programovací jazyk C#.

## <a name="before-you-begin"></a>Než začnete

### <a name="install-visual-studio"></a>Instalace sady Visual Studio

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) stránku a nainstalovat zdarma.

::: moniker-end

### <a name="choose-your-theme-optional"></a>Zvolte motiv (volitelné)

Tento rychlý úvodní kurz obsahuje snímky obrazovky, použít tmavý motiv. Pokud nepoužíváte tmavý motiv, ale chtěli, najdete v článku [přizpůsobit IDE sady Visual Studio a Editor](quickstart-personalize-the-ide.md) stránku a zjistěte, jak.

## <a name="create-a-project"></a>Vytvoření projektu

Pokud chcete začít, vytvoříte projekt webové aplikace ASP.NET Core. Typ projektu obsahuje všechny soubory šablony k vytvoření webové aplikace, než jste přidali ještě nic!

::: moniker range="vs-2017"

1. Otevřete Visual Studio 2017.

1. V horní nabídce zvolte **souboru** > **nový** > **projektu**.

1. V levém podokně **nový projekt** dialogového okna rozbalte **Visual C#** a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**. <br/><br/>Pojmenujte svůj soubor `HelloWorld` a zvolte **OK**.

   ![Vytvořit nový projekt webové aplikace ASP.NET Core pro jazyk C#](../ide/media/csharp-aspnet-choose-template-name-file.png)

   > [!NOTE]
   > Pokud se nezobrazí **.NET Core** kategorii šablony projektu, zvolte **otevřít instalační program Visual Studio** odkaz v levém podokně. (V závislosti na nastavení zobrazení může být potřeba stránku posunout, aby ji.)
   >
   > ![Otevřít instalační program sady Visual Studio z dialogového okna Nový projekt](../ide/media/open-visual-studio-installer.png)
   >
   > Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.
   >
   > ![Úlohy technologie ASP.NET v instalačním programu VS](../ide/media/quickstart-aspnet-workload.png)
   >
   > (Může mít ukončit sadu Visual Studio, abyste mohli pokračovat v instalaci nové úlohy.)

1. V **nová webová aplikace ASP.NET Core** dialogu **ASP.NET Core 2.1** z hlavní nabídky rozevíracího seznamu. Dále zvolte **webovou aplikaci**a klikněte na tlačítko **OK**.

   ![Dialogové okno nové webové aplikace ASP.NET Core](../ide/media/aspnet-core-2dot1.png)

   > [!NOTE]
   > Pokud nevidíte **ASP.NET Core 2.1**, ujistěte se, že používáte nejnovější verzi sady Visual Studio. Další informace o tom, jak aktualizovat vaši instalaci, najdete v článku [aktualizovat na nejnovější verzi aplikace Visual Studio](../install/update-visual-studio.md) stránky.

Brzy NATO Visual Studio otevře soubor projektu.

::: moniker-end

::: moniker range="vs-2019"

1. Otevřít Visual Studio.

1. V okně start zvolte **vytvořte nový projekt**.

   ![Zobrazit okno 'vytvořte nový projekt.](../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Na **vytvořte nový projekt** okno, zadejte nebo zadejte *ASP.NET* do vyhledávacího pole. Dále zvolte **C#** od jazyka seznamu a klikněte na tlačítko **Windows** ze seznamu platformy.

   Po použití filtrů jazyka a libovolné platformy, zvolte **webové aplikace ASP.NET Core** šablony a klikněte na tlačítko **Další**.

   ![Zvolte C# šablony pro webové aplikace ASP.NET Core](../get-started/csharp/media/vs-2019/csharp-create-new-project-search-aspnet-core-filtered.png)

   > [!NOTE]
   > Pokud se nezobrazí **webové aplikace ASP.NET Core** šablony, můžete jej nainstalovat z **vytvořte nový projekt** okna. V **nenašli, co hledáte?** zprávu, zvolte **nainstalovat další nástroje a funkce** odkaz.
   >
   > ![Odkaz "Nainstalovat další nástroje a funkce" z 'Nemůžete najít, co hledáte' zprávy v okně "vytvořit nový projekt.](../get-started/media/vs-2019/not-finding-what-looking-for.png)
   >
   > Pak ve Visual Studio Installer, zvolte **vývoj pro ASP.NET a web** pracovního vytížení.
   >
   > ![Úlohy základní webové aplikace ASP.NET v instalačním programu sady Visual Studio](../get-started/media/aspnet-core-web-dev-workload.png)
   >
   > Po tomto, zvolte **změnit** tlačítko v instalačním programu sady Visual Studio. Můžete být vyzváni k uložte svou práci; Pokud ano, udělejte to. Dále zvolte **pokračovat** instalace zatížení. Pak se vraťte ke kroku 2 v tomto "[vytvořte projekt](#create-a-project)" postup.

1. V **konfigurovat nový projekt** okno, zadejte nebo vložte *HelloWorld* v **název projektu** pole. Potom kliknutím na možnost **vytvořit**.

   ![v okně 'Konfigurace nového projektu' název projektu "Hello World"](../get-started/csharp/media/vs-2019/csharp-name-your-aspnet-helloworld-project.png)

1. V **vytvořit novou webovou aplikaci ASP.NET Core** okna, ověřte, že **ASP.NET Core 2.1** se zobrazí v horní nabídce rozevíracího seznamu. Potom kliknutím na možnost **webovou aplikaci**, který obsahuje příklad stránky Razor. Dále zvolte **vytvořit**.

   ![V okně "vytvořit novou webovou aplikaci ASP.NET Core.](../get-started/csharp/media/vs-2019/csharp-create-aspnet-core-razor-pages-app.png)

   Visual Studio otevře nový projekt.

::: moniker-end

## <a name="create-and-run-the-app"></a>Vytvoření a spuštění aplikace

1. V **Průzkumníka řešení**, rozbalte **stránky** složky a klikněte na tlačítko **About.cshtml**.

   ![Zvolte soubor About.cshtml z Průzkumníka řešení](../ide/media/csharp-aspnet-about-page-html-file.png)

   Tento soubor odpovídá na stránku s názvem **o** ve webové aplikaci, která se spouští ve webovém prohlížeči.

   ![Na stránce o ve webové aplikaci](../ide/media/csharp-aspnet-about-page.png)

   V editoru HTML zobrazí kód pro oblasti "Další informace" **o** stránky.

   ![Kód HTML pro další informace o oblasti v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-page.png)

1. Změní celý text "Další informace" číst "**Hello World!** ".

   ![Změnit výchozí kód HTML pro další informace o oblasti v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-page-hello-world.png)

1. V **Průzkumníka řešení**, rozbalte **About.cshtml**a klikněte na tlačítko **About.cshtml.cs**. (Tento soubor také odpovídá **o** stránku ve webovém prohlížeči.)

   ![Zvolte soubor About.cshtml z Průzkumníka řešení](../ide/media/csharp-aspnet-about-page-code-file.png)

   V editoru, zobrazí se vám C# kód, který obsahuje text "Popis aplikace" oblasti **o** stránky.

   ![Kód jazyka C# pro oblasti Popis aplikace v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-cs-code.png)

1. Změní celý text zprávy "Popis aplikace" číst "**jaká je Moje zpráva?** ".

   ![Změnit výchozí text zprávy pro oblasti Popis aplikace v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-cs-message.png)

1. Zvolte **služby IIS Express** nebo stiskněte klávesu **Ctrl**+**F5** ke spuštění aplikace a otevřete ho ve webovém prohlížeči.

   ![Vyberte tlačítko služby IIS Express v sadě Visual Studio](../ide/media/csharp-aspnet-helloworld-iisbutton.png)

   > [!NOTE]
   > Pokud se zobrazí chybová zpráva s upozorněním, **nelze se připojit k webovému serveru služby IIS Express**, nebo chybovou zprávu s odkazem na server certifikát SSL, zavřete sadu Visual Studio. Dále otevřete Visual Studio s použitím **spustit jako správce** možnost v místní nabídce klikněte pravým tlačítkem. Spusťte aplikaci znovu.

1. Ve webovém prohlížeči, ověřte, že **o** stránka obsahuje aktualizovaný text.

   ![Zobrazit aktualizovaný o stránku, která obsahuje změny, které jste provedli](../ide/media/csharp-aspnet-about-page-hello-world.png)

1. Zavřete webový prohlížeč.

### <a name="review-your-work"></a>Projděte si svou práci

Zobrazte následující animace zkontrolovat práci, kterou jste dokončili v předchozí části.

  ![Zobrazit animovaný obrázek GIF soubor, který ukazuje, jak vytvářet a spouštět jednoduchý C# webové aplikace ASP.NET Core v sadě Visual Studio](../ide/media/csharp-aspnet-animated-hello-world.gif)

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli ještě něco o jazyce C#, ASP.NET Core a Visual Studio IDE (integrované vývojové prostředí).

## <a name="next-steps"></a>Další kroky

Další informace najdete dál v následujícím kurzu:

> [!div class="nextstepaction"]
> [Začínáme s C# a technologie ASP.NET v sadě Visual Studio](../get-started/csharp/tutorial-aspnet-core.md)

## <a name="see-also"></a>Viz také:

[Publikování webové aplikace do služby Azure App Service pomocí sady Visual Studio](../deployment/quickstart-deploy-to-azure.md)

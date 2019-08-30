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
ms.openlocfilehash: 28994e7f3a4f31a9e3ee8c292a08df1132cf20df
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2019
ms.locfileid: "70180381"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Rychlý start: Vytvoření první ASP.NET Core webové aplikace pomocí sady Visual Studio

V tomto úvodu 5 až 10 minut na tom, jak pomocí sady Visual Studio vytvoříte jednoduchou webovou aplikaci "Hello World" pomocí šablony projektu ASP.NET a programovací jazyk C#.

## <a name="before-you-begin"></a>Než začnete

### <a name="install-visual-studio"></a>Instalace sady Visual Studio

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads) stránku a nainstalovat zdarma.

::: moniker-end

### <a name="choose-your-theme-optional"></a>Zvolte motiv (volitelné)

Tento rychlý úvodní kurz obsahuje snímky obrazovky, použít tmavý motiv. Pokud nepoužíváte tmavý motiv, ale chtěli, najdete v článku [přizpůsobit IDE sady Visual Studio a Editor](quickstart-personalize-the-ide.md) stránku a zjistěte, jak.

## <a name="create-a-project"></a>Vytvoření projektu

Pokud chcete začít, vytvoříte projekt webové aplikace ASP.NET Core. Typ projektu obsahuje všechny soubory šablon pro vytvoření webové aplikace, než dokonce cokoli přidáte.

::: moniker range="vs-2017"

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek vyberte **soubor** > **Nový** > **projekt**.

1. V levém podokně **nový projekt** dialogového okna rozbalte **Visual C#** a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**. <br/><br/>Pojmenujte svůj soubor `HelloWorld` a zvolte **OK**.

   ![Vytvořit nový projekt ASP.NET Core webové aplikace proC#](../ide/media/csharp-aspnet-choose-template-name-file.png)

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

1. V dialogovém okně **Nová webová aplikace ASP.NET Core** v horním rozevíracím seznamu vyberte **ASP.NET Core 2,1** . V dalším kroku zvolte možnost **Webová aplikace**a pak klikněte na **tlačítko OK**.

   ![Dialogové okno Nová webová aplikace ASP.NET Core](../ide/media/aspnet-core-2dot1.png)

   > [!NOTE]
   > Pokud nevidíte **ASP.NET Core 2,1**, ujistěte se, že používáte nejnovější verzi sady Visual Studio. Další informace o tom, jak aktualizovat instalaci, najdete na stránce o [aktualizaci sady Visual Studio na nejnovější verzi](../install/update-visual-studio.md) .

Brzy NATO Visual Studio otevře soubor projektu.

::: moniker-end

::: moniker range="vs-2019"

1. Otevřít Visual Studio.

1. V okně Start vyberte možnost **vytvořit nový projekt**.

   ![Zobrazit okno vytvořit nový projekt](../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. V okně **vytvořit nový projekt** zadejte nebo do vyhledávacího pole zadejte *ASP.NET* . Dále zvolte **C#** ze seznamu jazyk a v seznamu platforma zvolte možnost **Windows** .

   Po použití filtrů jazyků a platforem zvolte šablonu **ASP.NET Core webové aplikace** a klikněte na tlačítko **Další**.

   ![Zvolit C# šablonu pro ASP.NET Core webovou aplikaci](../get-started/csharp/media/vs-2019/csharp-create-new-project-search-aspnet-core-filtered.png)

   > [!NOTE]
   > Pokud nevidíte šablonu **ASP.NET Core webové aplikace** , můžete ji nainstalovat z okna **vytvořit nový projekt** . V části **nenajít, co hledáte?** klikněte na odkaz **instalovat další nástroje a funkce** .
   >
   > ![Odkaz pro instalaci dalších nástrojů a funkcí v okně vytvořit nový projekt v části nenajít, co hledáte?](../get-started/media/vs-2019/not-finding-what-looking-for.png)
   >
   > Pak v Instalační program pro Visual Studio zvolte úlohu **vývoje ASP.NET a web** .
   >
   > ![ASP.NET Core úlohy webové aplikace v Instalační program pro Visual Studio](../get-started/media/aspnet-core-web-dev-workload.png)
   >
   > Potom klikněte na tlačítko **Upravit** v instalační program pro Visual Studio. Může se zobrazit výzva k uložení práce; Pokud ano, udělejte to. V dalším kroku vyberte **pokračovat** a nainstalujte úlohu. Pak se vraťte ke kroku 2 v tomto postupu "[Vytvoření projektu](#create-a-project)".

1. V okně **Konfigurovat nový projekt** zadejte nebo zadejte *HelloWorld* do pole **název projektu** . Pak zvolte **vytvořit**.

   ![v okně Konfigurovat nový projekt pojmenujte svůj projekt HelloWorld.](../get-started/csharp/media/vs-2019/csharp-name-your-aspnet-helloworld-project.png)

1. V okně **vytvořit novou webovou aplikaci ASP.NET Core** ověřte, zda se v horní rozevírací nabídce zobrazí **ASP.NET Core 2,1** . Pak zvolte **Webová aplikace**, která obsahuje například Razor Pages. Pak vyberte **vytvořit**.

   ![Okno vytvořit novou ASP.NET Core webovou aplikaci](../get-started/csharp/media/vs-2019/csharp-create-aspnet-core-razor-pages-app.png)

   Visual Studio otevře nový projekt.

::: moniker-end

## <a name="create-and-run-the-app"></a>Vytvoření a spuštění aplikace

1. V **Průzkumník řešení**rozbalte složku **stránky** a zvolte možnost **o. cshtml**.

   ![Zvolte soubor About.cshtml z Průzkumníka řešení](../ide/media/csharp-aspnet-about-page-html-file.png)

   Tento soubor odpovídá na stránku s názvem **o** ve webové aplikaci, která se spouští ve webovém prohlížeči.

   ![Na stránce o ve webové aplikaci](../ide/media/csharp-aspnet-about-page.png)

   V editoru uvidíte kód HTML v oblasti "Další informace" na stránce **About** .

   ![Kód HTML pro doplňkovou oblast informací v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-page.png)

1. Změnou textu "Další informace" Přečtěte "**Hello World!** ".

   ![Změna výchozího kódu HTML pro další informace o oblasti v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-page-hello-world.png)

1. V **Průzkumníka řešení**, rozbalte **About.cshtml**a klikněte na tlačítko **About.cshtml.cs**. (Tento soubor také odpovídá stránce **o** stránku ve webovém prohlížeči.)

   ![Zvolte soubor About.cshtml z Průzkumníka řešení](../ide/media/csharp-aspnet-about-page-code-file.png)

   V editoru uvidíte C# kód, který obsahuje text pro oblast Popis aplikace na stránce **o produktu** .

   ![C# Kód oblasti Popis aplikace v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-cs-code.png)

1. Změní celý text zprávy "Popis aplikace" číst "**jaká je Moje zpráva?** ".

   ![Změna výchozího textu zprávy pro oblast popisu aplikace v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-cs-message.png)

1. Zvolte **služby IIS Express** nebo stiskněte klávesu **Ctrl**+**F5** ke spuštění aplikace a otevřete ho ve webovém prohlížeči.

   ![Výběr tlačítka IIS Express v aplikaci Visual Studio](../ide/media/csharp-aspnet-helloworld-iisbutton.png)

   > [!NOTE]
   > Pokud se zobrazí chybová zpráva s upozorněním, **nelze se připojit k webovému serveru služby IIS Express**, nebo chybovou zprávu s odkazem na server certifikát SSL, zavřete sadu Visual Studio. Dále otevřete aplikaci Visual Studio pomocí možnosti **Spustit jako správce** z místní nabídky klikněte pravým tlačítkem myši. Spusťte aplikaci znovu.

1. Ve webovém prohlížeči, ověřte, že **o** stránka obsahuje aktualizovaný text.

   ![Zobrazit aktualizované informace o stránce, která obsahuje změny, které jste provedli](../ide/media/csharp-aspnet-about-page-hello-world.png)

1. Zavřete webový prohlížeč.

### <a name="review-your-work"></a>Kontrola práce

Prohlédněte si následující animaci a zkontrolujte práci, kterou jste dokončili v předchozí části.

  ![Podívejte se na animovaný soubor. gif, který ukazuje, jak vytvořit a spustit C# jednoduchou webovou aplikaci ASP.NET Core v aplikaci Visual Studio.](../ide/media/csharp-aspnet-animated-hello-world.gif)

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli ještě něco o jazyce C#, ASP.NET Core a Visual Studio IDE (integrované vývojové prostředí).

## <a name="next-steps"></a>Další kroky

Další informace najdete dál v následujícím kurzu:

> [!div class="nextstepaction"]
> [Začínáme s C# a technologie ASP.NET v sadě Visual Studio](../get-started/csharp/tutorial-aspnet-core.md)

## <a name="see-also"></a>Viz také:

[Publikování webové aplikace do služby Azure App Service pomocí sady Visual Studio](../deployment/quickstart-deploy-to-azure.md)

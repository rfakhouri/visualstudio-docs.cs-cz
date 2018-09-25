---
title: Vytvoření webové aplikace ASP.NET Core v jazyce C# pomocí sady Visual Studio
description: Zjistěte, jak vytvořit jednoduchou webovou aplikaci Hello World v sadě Visual Studio s C# a ASP.NET Core, krok za krokem.
ms.custom: mvc
ms.date: 09/23/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: quickstart
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 53bed90ea686897c2a668ddbc64c60a95c8edfe8
ms.sourcegitcommit: 25fc9605ba673afb51a24ce587cf4304b06aa577
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2018
ms.locfileid: "47028933"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Rychlý start: Použití sady Visual Studio k vytvoření vaší první webové aplikace ASP.NET Core

V tomto úvodu 5 až 10 minut na tom, jak pomocí sady Visual Studio vytvoříte jednoduchou webovou aplikaci "Hello World" pomocí šablony projektu ASP.NET a programovací jazyk C#.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt webové aplikace ASP.NET Core. Tady je způsob.

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

1. V levém podokně **nový projekt** dialogového okna rozbalte **Visual C#** a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**. Pojmenujte svůj soubor `HelloWorld` a zvolte **OK**.

1. V **nová webová aplikace ASP.NET Core** dialogovém okně ověřte, zda **ASP.NET Core 2.0** se zobrazí v horní nabídce rozevíracího seznamu. Potom kliknutím na možnost **webovou aplikaci** a zvolte **OK**.

   ![Zobrazit animovaný obrázek GIF soubor, který ukazuje, jak vytvořit projekt C# ASP.NET Core v sadě Visual Studio](../ide/media/csharp-aspnet-animated-create-project.gif)

   Brzy NATO Visual Studio otevře soubor projektu.

   > [!NOTE]
   > Pokud se nezobrazí **.NET Core** kategorii šablony projektu, zvolte **otevřít instalační program Visual Studio** odkaz v levém podokně.
   >
   > ![Otevřít instalační program sady Visual Studio z dialogového okna Nový projekt](../ide/media/open-visual-studio-installer.png)
   >
   > Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úlohy a klikněte na tlačítko **změnit**.
   >
   > ![Úlohy technologie ASP.NET v instalačním programu VS](../ide/media/quickstart-aspnet-workload.png)
   >
   > (Může mít ukončit sadu Visual Studio, abyste mohli pokračovat v instalaci nové úlohy.)

## <a name="create-and-run-the-app"></a>Vytvoření a spuštění aplikace

V dalším kroku vytvoříte a spouštění vaší webové aplikace "Hello World". Tady je způsob.

1. V sadě Visual Studio v **Průzkumníka řešení**, rozbalte **stránky** složky. Potom kliknutím na možnost **About.cshtml**.

   ![Zvolte soubor About.cshtml z Průzkumníka řešení](../ide/media/csharp-aspnet-about-page-html-file.png)

   Tento soubor odpovídá na stránku s názvem **o** ve webové aplikaci, která se spouští ve webovém prohlížeči.

   ![Na stránce o ve webové aplikaci](../ide/media/csharp-aspnet-about-page.png)

1. V editoru kódu sady Visual Studio změní celý text "Další informace" číst "**Hello World!**".

1. V **Průzkumníka řešení**, rozbalte **About.cshtml**a klikněte na tlačítko **About.cshtml.cs**.

1. Změní celý text zprávy "Popis aplikace" číst "**jaká je Moje zpráva?**".

1. Zvolte **služby IIS Express** nebo stiskněte klávesu **Ctrl**+**F5** ke spuštění aplikace a otevřete ho ve webovém prohlížeči.

   ![Zobrazit animovaný obrázek GIF soubor, který ukazuje, jak vytvářet a spouštět webovou aplikaci C# ASP.NET Core v sadě Visual Studio](../ide/media/csharp-aspnet-animated-hello-world.gif)

   > [!NOTE]
   > Pokud se zobrazí chybová zpráva s upozorněním, **nelze se připojit k webovému serveru služby IIS Express**, zavřete sadu Visual Studio a otevřete jej pomocí **spustit jako správce** možnost v nabídce klikněte pravým tlačítkem nebo kontext. Spusťte aplikaci znovu.

1. Ve webovém prohlížeči, ověřte, že **o** stránka obsahuje aktualizovaný text.

1. Zavřete webový prohlížeč.

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli ještě něco o jazyce C#, ASP.NET Core a Visual Studio IDE (integrované vývojové prostředí).

## <a name="next-steps"></a>Další kroky

Další informace najdete dál v následujícím kurzu:

> [!div class="nextstepaction"]
> [Začínáme s C# a technologie ASP.NET v sadě Visual Studio](tutorial-csharp-aspnet-core.md)

## <a name="see-also"></a>Viz také:

[Publikování webové aplikace do služby Azure App Service pomocí sady Visual Studio](..//deployment/quickstart-deploy-to-azure.md)

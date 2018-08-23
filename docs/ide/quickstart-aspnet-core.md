---
title: Vytvoření webové aplikace ASP.NET Core v jazyce C# pomocí sady Visual Studio
description: Zjistěte, jak vytvořit jednoduchou webovou aplikaci Hello World v sadě Visual Studio s C# a ASP.NET Core, krok za krokem.
ms.custom: mvc
ms.date: 07/20/2018
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
ms.openlocfilehash: 189e4b9751498b79c8d74568c423946459fabbd5
ms.sourcegitcommit: 9e796d8a8b737ed9d5bf024db89b1abf99ea809b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/21/2018
ms.locfileid: "42624214"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Rychlý start: Použití sady Visual Studio k vytvoření vaší první webové aplikace ASP.NET Core

V tomto úvodu 5 až 10 minut na tom, jak pomocí sady Visual Studio vytvoříte jednoduchou webovou aplikaci "Hello World" pomocí šablony projektu ASP.NET a programovací jazyk C#.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt webové aplikace ASP.NET Core. Typ projektu obsahuje všechny soubory šablony k vytvoření webové aplikace, než jste přidali ještě nic!

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

1. V levém podokně **nový projekt** dialogového okna rozbalte **Visual C#** a klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**. Pojmenujte svůj soubor `HelloWorld` a zvolte **OK**.

   ![Vytvořit nový projekt webové aplikace ASP.NET Core pro jazyk C#](../ide/media/csharp-aspnet-choose-template-name-file.png)

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

1. V **nová webová aplikace ASP.NET Core** dialogovém okně ověřte, zda **ASP.NET Core 2.0** se zobrazí v horní nabídce rozevíracího seznamu. Potom kliknutím na možnost **webovou aplikaci** a zvolte **OK**.

   ![Dialogové okno nové webové aplikace ASP.NET Core](../ide/media/quickstart-aspnet-core20.png)

Brzy NATO Visual Studio otevře soubor projektu.

## <a name="create-the-app"></a>Vytvoření aplikace

1. V **Průzkumníka řešení**, rozbalte **stránky** složky a klikněte na tlačítko **About.cshtml**.

   ![Zvolte soubor About.cshtml z Průzkumníka řešení](../ide/media/csharp-aspnet-about-page-html-file.png)

   Tento soubor odpovídá na stránku s názvem **o** ve webové aplikaci.

   ![Na stránce o ve webové aplikaci](../ide/media/csharp-aspnet-about-page.png)

   V editoru HTML zobrazí kód pro oblasti "Další informace" **o** stránky.

   ![Kód HTML pro další informace o oblasti v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-page.png)

1. Změní celý text "Další informace" číst "**Hello World!**".

   ![Změnit výchozí kód HTML pro další informace o oblasti v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-page-hello-world.png)

1. V **Průzkumníka řešení**, rozbalte **About.cshtml**a klikněte na tlačítko **About.cshtml.cs**. (Tento soubor také odpovídá **o** stránka ve webové aplikaci.)

   ![Zvolte soubor About.cshtml z Průzkumníka řešení](../ide/media/csharp-aspnet-about-page-code-file.png)

   V editoru, zobrazí se vám C# kód, který obsahuje text "Popis aplikace" oblasti **o** stránky.

   ![Kód jazyka C# pro oblasti Popis aplikace v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-cs-code.png)

1. Změní celý text zprávy "Popis aplikace" číst "**jaká je Moje zpráva?**".

   ![Změnit výchozí text zprávy pro oblasti Popis aplikace v editoru sady Visual Studio](../ide/media/csharp-aspnet-about-cshtml-cs-message.png)

## <a name="run-the-app"></a>Spuštění aplikace

1. Stisknutím klávesy **Ctrl**+**F5** ke spuštění aplikace a otevřete ho ve webovém prohlížeči.

   > [!NOTE]
   > Pokud se zobrazí chybová zpráva s upozorněním, **nelze se připojit k webovému serveru služby IIS Express**, zavřete sadu Visual Studio a otevřete jej pomocí **spustit jako správce** možnost v nabídce klikněte pravým tlačítkem nebo kontext. Spusťte aplikaci znovu.

1. V horní části webové stránky, zvolte **o**.

   ![Vyberte o z webové stránky](../ide/media/csharp-aspnet-home-page-about.png)

1. Zobrazení aktualizované text, který jste přidali do **o** stránky.

   ![Zobrazit aktualizované informace o stránce obsahující text, který jste přidali](../ide/media/csharp-aspnet-about-page-hello-world.png)

1. Zavřete webový prohlížeč.

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli ještě něco o jazyce C#, ASP.NET Core a Visual Studio IDE (integrované vývojové prostředí).

## <a name="next-steps"></a>Další kroky

Další informace najdete dál v následujícím kurzu:

> [!div class="nextstepaction"]
> [Začínáme s C# a technologie ASP.NET v sadě Visual Studio](tutorial-csharp-aspnet-core.md)

## <a name="see-also"></a>Viz také:

[Publikování webové aplikace do služby Azure App Service pomocí sady Visual Studio](..//deployment/quickstart-deploy-to-azure.md)

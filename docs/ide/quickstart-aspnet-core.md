---
title: Vytvoření webové aplikace ASP.NET Core v jazyce C# pomocí sady Visual Studio
description: Zjistěte, jak vytvořit webovou aplikaci ASP.NET Core v sadě Visual Studio s C#, krok za krokem.
ms.custom: mvc
ms.date: 06/27/2018
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
ms.openlocfilehash: 83811499782fedd5b869ca6587a6d13d60af187d
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176301"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Rychlý start: Použití sady Visual Studio k vytvoření vaší první webové aplikace ASP.NET Core

V tomto úvodu 5 až 10 minut do integrovaného vývojového prostředí (IDE) sady Visual Studio vytvoříte jednoduchou webovou aplikaci C# ASP.NET Core.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt webové aplikace ASP.NET Core. Typ projektu je součástí souborů šablon, které tvoří funkční webovou aplikaci, než jste přidali ještě nic!

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **Visual C#**, klikněte na tlačítko **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**, klikněte na tlačítko **OK**.

     Pokud se nezobrazí **.NET Core** kategorii šablony projektu, zvolte **otevřít instalační program Visual Studio** odkaz v levém podokně. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úloh, klikněte na tlačítko **změnit**.

     ![Úlohy technologie ASP.NET v instalačním programu VS](../ide/media/quickstart-aspnet-workload.png)

1. V **nová webová aplikace ASP.NET Core** dialogu **ASP.NET Core 2.0** z hlavní nabídky rozevíracího seznamu. (Pokud se nezobrazí **ASP.NET Core 2.0** v seznamu, nainstalujte ji pomocí následujících **Stáhnout** odkaz, který by se měla objevit v žlutý pruh v horní části dialogu.) Zvolte **OK**.

   ![Dialogové okno nové webové aplikace ASP.NET Core](../ide/media/quickstart-aspnet-core20.png)

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE

1. V **Průzkumníka řešení** nástrojů, rozbalte **stránky** složky, klikněte na tlačítko **About.cshtml** ho otevřete v editoru. Tento soubor odpovídá stránku s názvem **o** ve webové aplikaci.

1. V editoru zvolte `AboutModel` a potom stiskněte klávesu **F12** nebo zvolte **přejít k definici** (klikněte pravým tlačítkem) místní nabídce. Tento příkaz má definici typu `AboutModel` třída jazyka C#.

   ![Přejít k definici kontextové nabídky](../ide/media/quickstart-aspnet-gotodefinition.png)

1. Další čištění `using` direktivy v horní části souboru pomocí jednoduchého zástupce. Vybrat kteroukoli z šedě direktiv using a [rychlé akce](../ide/quick-actions.md) žárovka se zobrazí pod blikajícím kurzorem nebo na levém okraji. Zvolte žárovku a pak zvolte **odebrat nepotřebné direktivy using**.

     Ze souboru budou odstraněny nepotřebné direktivy using.

1. V `OnGet()` metodu, změňte obsah následujícím kódem:

 ```csharp
 public void OnGet()
 {
     string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
 }
 ```

1. Zobrazí se vám zobrazí v rámci dvou podtržení vlnovkou **prostředí** a **řetězec**, protože tyto typy nejsou v oboru. Otevřít **seznam chyb** nástrojů se zobrazí stejné chyby uvedeny zde. (Pokud se nezobrazí **seznam chyb** nástrojů, zvolte **zobrazení** > **seznam chyb** v horní nabídce.)

   ![Seznam chyb](../ide/media/quickstart-aspnet-errorlist.png)

1. V okně editoru umístěte kurzor na buď řádku, který obsahuje chybu a pak zvolte levý okraj žárovky rychlé akce. Z rozevírací nabídky vyberte **pomocí systému;** případné chyby opravte a přidejte tuto direktivu do horní části souboru.

## <a name="run-the-application"></a>Spuštění aplikace

1. Stisknutím klávesy **Ctrl**+**F5** ke spuštění aplikace a otevřete ho ve webovém prohlížeči.

1. V horní části stránky na webu, zvolte **o** zobrazíte zprávu jste přidali v adresáři `OnGet()` metodu **o** stránky.

1. Zavřete webový prohlížeč.

> [!NOTE]
> Pokud se zobrazí chybová zpráva s upozorněním **nelze se připojit k webovému serveru služby IIS Express**, zavřete sadu Visual Studio a otevřete jej pomocí **spustit jako správce** možnost v nabídce klikněte pravým tlačítkem nebo kontext. Spusťte aplikaci znovu.

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli ještě něco o integrovaném vývojovém prostředí sady Visual Studio. Pokud jste chtěli delve hlouběji do jeho funkce, prosím pokračujte kurz **kurzy** část obsahu.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli ještě něco o jazyce C#, ASP.NET Core a integrovaném vývojovém prostředí sady Visual Studio. Pokud chcete zobrazit aplikaci spuštěnou na veřejný server, vyberte na následující tlačítko.

> [!div class="nextstepaction"]
> [Nasaďte aplikaci do služby Azure App Service](..//deployment/quickstart-deploy-to-azure.md)

Další informace, pokračujte v kurzech [Začínáme s C# a technologie ASP.NET v sadě Visual Studio](tutorial-csharp-aspnet-core.md) a [Začínáme s ASP.NET Core MVC a sady Visual Studio](/aspnet/core/tutorials/first-mvc-app/start-mvc?tabs=aspnetcore2x).

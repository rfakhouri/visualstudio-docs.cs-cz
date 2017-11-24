---
title: "Použijte sadu Visual Studio k vytvoření webové aplikace ASP.NET Core v jazyce C# | Microsoft Docs"
ms.custom: 
ms.date: 10/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: CSharp
ms.openlocfilehash: 6879d29b1e8c36ce9456fc44cf738a57603a6d50
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2017
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Rychlý úvod: použijte sadu Visual Studio k vytvoření první webové aplikace ASP.NET Core

V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou webovou aplikaci ASP.NET Core C#. Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).

## <a name="create-a-project"></a>Vytvoření projektu

Nejdřív vytvoříte projekt webové aplikace technologie ASP.NET Core. Typ projektu se dodává s soubory šablon, které tvoří funkční webovou aplikaci, než jste přidali i nic!

1. Otevřete Visual Studio 2017.

1. V horní nabídce vyberte příkaz **soubor**, **nový**, **projektu...** .

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **Visual C#**, zvolte **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**, zvolte **OK**.

     Pokud nevidíte **.NET Core** projektu šablony, zrušte mimo **nový projekt** dialogové okno a z panelu horní nabídce zvolte **nástroje**, **získat nástroje a Funkce...** . Spustí instalační program Visual Studio. Vyberte **ASP.NET a webové vývoj** zatížení, zvolte **upravit**.

     ![Zatížení technologie ASP.NET v instalační program VS](../ide/media/quickstart-aspnet-workload.png)

1. V **nové webové aplikace ASP.NET Core** dialogové okno, vyberte **technologii ASP.NET 2.0 základní** v hlavní nabídce rozevíracího seznamu. (Pokud nevidíte **technologii ASP.NET 2.0 základní** v seznamu, nainstalujte ji podle **Stáhnout** odkaz, který by se měla objevit v žlutý pruh v horní části dialogové okno.) Zvolte **OK**.

   ![Nové webové aplikace ASP.NET Core dialogbox](../ide/media/quickstart-aspnet-core20.png)

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE

1. V **Průzkumníku řešení** nástrojů, rozbalte **stránky** složku, pak zvolte **About.cshtml** a otevře se v editoru. Tento soubor odpovídá stránku s názvem **o** ve webové aplikaci.

1. V editoru, zvolte `AboutModel` a potom stiskněte klávesu **F12** nebo zvolte **přejít k definici** z nabídky kontextu (klikněte pravým tlačítkem). Tento příkaz má definici `AboutModel` třída jazyka C#.

   ![Přejít k definici kontextové nabídky](../ide/media/quickstart-aspnet-gotodefinition.png)

1. Potom jsme budete vyčištění `using` direktivy v horní části souboru pomocí jednoduchého zástupce. Vybrat kteroukoli z aktivní out pomocí direktiv a [rychlé akce](../ide/quick-actions.md) žárovky se zobrazí pod vsuvka nebo na levém okraji. Zvolte žárovky a potom vyberte **odeberte nepotřebné direktiv Using**.

     Nepotřebné direktiv Using se odstraní ze souboru.

1. V `OnGet()` metoda, změňte obsah pro následující kód:

 ```csharp
 public void OnGet()
 {
     string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
 }
 ```

1. Uvidíte dvě podtržení vlnovkami vyskytovat v části **prostředí** a **řetězec**, protože tyto typy nejsou v oboru. Otevřete **seznam chyb** nezobrazí nástrojů najdete v části stejné chyby. (Pokud se nezobrazí **seznam chyb** nástrojů vyberte **zobrazení**, **seznam chyb** z hlavní nabídky panelu.)

   ![Seznam chyb](../ide/media/quickstart-aspnet-errorlist.png)

1. V okně editoru umístěte kurzor na buď řádek, který obsahuje chybu, a potom vyberte žárovky rychlé akce na levém okraji. Z rozevírací nabídky vyberte **pomocí systému;** na začátek souboru přidejte tato direktiva a případné chyby opravte.

## <a name="run-the-application"></a>Spuštění aplikace

1. Stiskněte klávesu **Ctrl + F5** otevřete ve webovém prohlížeči a spusťte aplikaci.

1. V horní části webu, zvolte **o** zobrazíte zprávy jste přidali v adresáři `OnGet()` metodu pro **o** stránky.

1. Zavřete webový prohlížeč.

Blahopřejeme k dokončení tento rychlý start! Věříme, že jste se naučili chvíli o prostředí Visual Studio IDE. Pokud chcete pustíte hlubší do jeho možnosti, pokračujte prosím se v kurzu **kurzy** části obsahu.

## <a name="see-also"></a>Viz také

[Začínáme s C# a Visual Basic pomocí sady Visual Studio](getting-started-with-visual-csharp-and-visual-basic.md)  
[Začínáme s stránky Razor v ASP.NET Core](/aspnet/core/tutorials/razor-pages/razor-pages-start)
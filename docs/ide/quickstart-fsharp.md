---
title: 'Rychlý start: Vytvoření webové služby ASP.NET Core vF#'
description: Naučte se, jak vytvořit webovou službu ASP.NET Core v aplikaci Visual F#Studio s nástrojem, krok za krokem.
ms.date: 08/24/2018
ms.topic: quickstart
author: cartermp
ms.author: phcart
manager: andrehal
dev_langs:
- FSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 990106f7f3ca97ae38a20170ca6ed2e1d699d4e4
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2019
ms.locfileid: "70180326"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-service-in-f"></a>Rychlý start: Použijte Visual Studio k vytvoření první ASP.NET Core webové služby v F\#

V tomto 5-10 minutách Úvod do F# sady Visual Studio vytvoříte webovou aplikaci F# ASP.NET Core.

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range="vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads) stránku a nainstalovat zdarma.

::: moniker-end

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt webového rozhraní API ASP.NET Core. Typ projektu je dodáván se soubory šablon, které představují funkční webovou službu, ještě před tím, než jste dokonce přidali cokoli!

::: moniker range="vs-2017"

1. Otevřít Visual Studio.

2. V horním řádku nabídek vyberte **soubor** > **Nový** > **projekt**.

3. V dialogovém okně **Nový projekt** rozbalte v levém podokně položku **vizuál F#** a pak zvolte možnost **Web**. V prostředním podokně zvolte **ASP.NET Core webová aplikace**a pak zvolte **OK**.

     Pokud se nezobrazí **.NET Core** kategorii šablony projektu, zvolte **otevřít instalační program Visual Studio** odkaz v levém podokně. Spustí se instalační program pro Visual Studio. Zvolte úlohu **vývoje ASP.NET a webu a** pak zvolte **Upravit**.

     ![Úlohy technologie ASP.NET v instalačním programu VS](../ide/media/quickstart-aspnet-workload.png)

4.In dialogového okna **Nová webová aplikace ASP.NET Core** vyberte v horním rozevíracím seznamu **ASP.NET Core 2,1** . (Pokud v seznamu nevidíte **ASP.NET Core 2,1** , nainstalujte ji pomocí odkazu **ke stažení** , který by se měl zobrazit ve žlutém panelu v horní části dialogového okna.) Zvolte **OK**.

::: moniker-end

::: moniker range=">=vs-2019"

1. Otevřít Visual Studio.

2. V okně Start vyberte možnost **vytvořit nový projekt**.

3. Na stránce **vytvořit nový projekt** zadejte do vyhledávacího pole **Web f #** a pak zvolte šablonu projektu **ASP.NET Core webové aplikace** . Zvolte **Další**.

4. Na stránce **Konfigurace nového projektu** zadejte název a pak zvolte **vytvořit**.

5. Na stránce **vytvořit novou webovou aplikaci ASP.NET Core** v horním rozevírací nabídce vyberte **ASP.NET Core 2,1** a pak zvolte **vytvořit**.

::: moniker-end

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE

1. Na panelu nástrojů **Průzkumník řešení** rozbalte složku **řadiče** a pak zvolte **ValuesController. FS** a otevřete ji v editoru.

   ![Průzkumník řešení s rozbalenou složkou F# Controllers v projektu webového rozhraní API](../ide/media/hello-world-fs-sln-explorer.png)

2. Dále upravte `Get()` člena tak, aby byl následující:

   ```fsharp
   [<HttpGet>]
   member this.Get() =
       let values = [|"Hello"; "World"; "First F#/ASP.NET Core web API!"|]
       ActionResult<string[]>(values)
   ```

Kód je jednoduchý. F# Pole hodnot je vázáno na `values` název a poté předáno do ASP.NET Core rozhraní `ActionResult`MVC jako. ASP.NET Core postará o zbytek za vás.

Mělo by to vypadat jako v editoru:

![Změněný člen get](../ide/media/hello-world-fs-get-member.png)

## <a name="run-the-application"></a>Spuštění aplikace

1. Stisknutím klávesy **CTRL**+**F5** spusťte aplikaci a otevřete ji ve webovém prohlížeči.

2. Stránka by měla přejít na `/api/values` trasu, ale pokud ne, zadejte `https://localhost:44396/api/values` do svého prohlížeče.

Ve webovém prohlížeči se teď zobrazí shoda formátu JSON, co jste zadali dříve.

## <a name="next-steps"></a>Další postup

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se dozvěděli F#trochu o, ASP.NET Core a integrovaném vývojovém prostředí sady Visual Studio. Pokud chcete zobrazit aplikaci běžící na veřejném serveru, vyberte následující tlačítko.

> [!div class="nextstepaction"]
> [Nasaďte aplikaci do služby Azure App Service](../deployment/quickstart-deploy-to-azure.md)

Pokud se chcete dozvědět F#víc, podívejte se na [ F# ](/dotnet/fsharp/index)oficiální příručku.
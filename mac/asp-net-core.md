---
title: Začínáme s ASP.NET Core
description: Tento článek popisuje, jak začít pracovat s technologií ASP.NET v sadě Visual Studio pro Mac, včetně instalace a vytvoření nového projektu.
author: asb3993
ms.author: amburns
ms.date: 07/13/2017
ms.assetid: 6E8B0C90-33D6-4546-8207-CE0787584565
ms.openlocfilehash: a4f85c4efee469901088c89436f1021e13f5ca90
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="getting-started-with-aspnet-core"></a>Začínáme s ASP.NET Core

 Visual Studio pro Mac usnadňuje vývoj vaší aplikace služby s jeho podporu pro platformu pro vývoj nejnovější základní technologie ASP.NET. ASP.NET Core běží na .NET Core, nejnovější vývoj rozhraní .NET Framework a prostředí runtime. Má byla optimalizovaných pro vysoký výkon, promítnou malé instalace velikostí a nové podobě ke spuštění na systému Linux a systému macOS, jakož i Windows.

## <a name="installing-net-core"></a>Instalaci .NET Core

.NET core 1.1 se automaticky nainstaluje při instalaci sady Visual Studio for Mac.

## <a name="creating-an-aspnet-core-app-in-visual-studio-for-mac"></a>Vytvoření aplikace ASP.NET Core v sadě Visual Studio pro Mac

Otevřete Visual Studio for Mac. Na úvodní stránce vyberte **nový projekt...**

![Dialogové okno Nový projekt](media/asp-net-core-image1.png)

Zobrazí se dialogové okno Nový projekt, což vám umožní vybrat šablonu pro vytvoření aplikace.

Existuje několik projektů, které vám poskytne předdefinovaných šablonu, která má začít vytvářet aplikace ASP.NET Core. Jsou to:

- **.NET core > prázdná webová aplikace ASP.NET Core**
- **.NET core > webové aplikace ASP.NET Core**
- **.NET core > ASP.NET Core webového rozhraní API**
- **Více platformami > aplikace > připojené aplikace**

![Možnosti projektu ASP.NET](media/asp-net-core-image11.png)

Vyberte **ASP.NET Core prázdné webové aplikace** a stiskněte klávesu **Další**. Poskytnout projektu název a stiskněte klávesu **vytvořit**. Tím se vytvoří novou aplikaci ASP.NET Core, která by měla vypadat podobně jako na následujícím obrázku:

![Nové zobrazení prázdný projekt ASP.NET Core](media/asp-net-core-image4.png)

Jádro ASP.NET prázdný webové aplikace vytvoří webovou aplikaci s dvě výchozí soubory: **Program.cs** a **Startup.cs**, které jsou vysvětleny níže. Vytvoří také závislosti složky, která obsahuje závislosti balíčků NuGet pro projekt jako je jádro ASP.NET, rozhraní .NET Core a cíle MSBuild, které se projekt sestavil:

![Zobrazení závislostí Pad řešení](media/asp-net-core-image12.png)

### <a name="programcs"></a>Program.cs

Otevřít a zkontrolovat **Program.cs** soubor ve vašem projektu. Všimněte si, že dvě věci se děje v `Main` metoda – záznam do vaší aplikace:

```csharp
public static void Main(string[] args)
{
    var host = new WebHostBuilder()
        .UseKestrel()
        .UseContentRoot(Directory.GetCurrentDirectory())
        .UseIISIntegration()
        .UseStartup<Startup>()
        .Build();

    host.Run();
}
```
Aplikace ASP.NET Core vytvoří webový server v jeho hlavní metoda konfigurace a spuštění hostitele přes instanci [ `WebHostBuilder` ](https://docs.microsoft.com/aspnet/core/fundamentals/hosting). Tohoto Tvůrce poskytuje metody, které umožňují hostitele nakonfigurovat. V šabloně aplikace se používají následující konfigurace:

 * `UseKestrel`: Určuje, že Kestrel server se použije v aplikaci
 * `UseContentRoot(Directory.GetCurrentDirectory())`: Používá webový projekt kořenové složky jako kořenový obsah aplikace při spuštění aplikace z této složky
 * `.UseIISIntegration()`: Určuje, že aplikace by měla fungovat s služby IIS. Použití služby IIS s ASP.NET Core `UseKestrel` a `UseIISIntegration` je potřeba zadat.
 * `.UseStartup<Startup>()`: Určuje třída při spuštění.

 Sestavení a spuštění metody sestavení IWebHost, který bude hostitelem aplikace a spusťte ji naslouchá příchozím požadavkům HTTP.

### <a name="startupcs"></a>Startup.cs

Třída při spuštění pro vaši aplikaci je uveden v `UseStartup()` metodu `WebHostBuilder`. Je v této třídě, kterou specifikujete žádost zpracování kanálu, a kde nakonfigurujete všechny služby.

Otevřít a zkontrolovat **Startup.cs** soubor ve vašem projektu:

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddConsole();

        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }

        app.Run(async (context) =>
        {
            await context.Response.WriteAsync("Hello World!");
        });
    }
}
```

Tato třída spuštění vždy musí splňovat následující pravidla:

 - Musí být vždy veřejné
 - Musí obsahovat dvě veřejné metody: `ConfigureServices` a `Configure`

`ConfigureServices` Metoda definuje služby, které budou používat vaši aplikaci.

`Configure` Můžete vytvořit pomocí kanálu požadavku [Middleware](https://docs.microsoft.com/aspnet/core/fundamentals/middleware). Jsou to komponenty použít v kanálu aplikace ASP.NET ke zpracování požadavků a odpovědí. Kanál protokolu HTTP se skládá z několika delegáti požadavku, volá se v pořadí. Každý delegát můžete buď zpracování požadavku sám sebe nebo předat další delegáta.

Delegáti můžete nakonfigurovat pomocí `Run`,`Map`, a `Use` metody na `IApplicationBuilder`, ale `Run` metoda bude nikdy volat další delegáta a by se měl na konci vašeho kanálu.

`Configure` Metoda předem připravených šablon vychází udělat pár věcí. Nejprve nakonfiguruje zpracování stránku pro použití při vývoji výjimek. Pak odešle odpověď na vyžádání webovou stránku s jednoduchý "Hello, World".

Tento jednoduchý Hello, World projektu můžete spustit nyní bez žádný další kód, který chcete přidat. Spuštění aplikace a zobrazit v prohlížeči, kliknutím na tlačítko Přehrát (trojstranný) na panelu nástrojů:

![Spuštění aplikace](media/asp-net-core-image5.png)

Visual Studio pro Mac používá náhodný port ke spuštění webového projektu. Chcete zjistit, co je to port je, otevřete aplikaci výstupu, který je uveden v části **zobrazení > dotyková zařízení**. Výstup by měl zjistit podobná následující:

![Zobrazení port naslouchání výstup aplikace](media/asp-net-core-image6.png)

Otevřete prohlížeč, výběru a zadejte `http://localhost:5000/`, a nahraďte `5000` s port, který Visual Studio výstup ve výstupu aplikace. Měli byste vidět text `Hello World!`:

![prohlížeč zobrazující text](media/asp-net-core-image7.png)

## <a name="adding-a-controller"></a>Přidání Kontroleru

Aplikace ASP.NET Core pomocí vzoru návrhu Model-View-Controller (MVC) poskytuje logického oddělení povinností mezi jednotlivých součástí aplikace. MVC se skládá z následujících akcí:

- **Model**: třída, která představuje data aplikace.
- **Zobrazení**: Zobrazí uživatelské rozhraní aplikace (což je často data modelu).
- **Řadič**: třída, která zpracovává požadavky na prohlížeč, odpoví na vstup uživatele a interakce.

Další informace o použití MVC najdete v části [přehled ASP.NET Core MVC](https://docs.microsoft.com/aspnet/core/mvc/overview) průvodce.

Pokud chcete přidat řadič, postupujte takto:

1. Klikněte pravým tlačítkem na název projektu a vyberte **Přidat > nové soubory**. Vyberte **Obecné > prázdné třídy**a zadejte název řadiče:

    ![Dialogové okno Nový soubor](media/asp-net-core-image8.png)

2. Přidejte následující kód na nový řadič:

    ```
    using System;
    using Microsoft.AspNetCore.Mvc;
    using System.Text.Encodings.Web;

    namespace Hello_ASP
    {
        public class HelloWorldController : Controller
        {
            //
            // GET: /HelloWorld/

            public string Index()
            {
                return "This is my default action...";
            }

        }
    }
    ```

3. Přidat `Microsoft.AspNetCore.Mvc` závislost na projekt kliknete pravým tlačítkem **závislostí** složku a výběr **přidat balíček...** .

4. Pomocí vyhledávacího pole a vyhledejte knihovně NuGet pro `Microsoft.AspNetCore.Mvc`a vyberte **přidat balíček**. To může trvat několik minut k instalaci a které může být vyzvání k přijetí různé licencí pro požadované závislosti:

    ![Přidat Nuget](media/asp-net-core-image9.png)

5. Ve třídě, spuštění, odeberte `app.Run` lambda a sadu logice směrování URL MVC používá k určení, který ho kódu by měla vyvolat pro následující:

    ```csharp
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=HelloWorld}/{action=Index}/{id?}");
    });
    ```

    Je třeba odstranit `app.Run` lambda, jako to přepíše logice směrování.

    Následujícím formátu, aplikace MVC používá k určení spuštění kódu:

    `/[Controller]/[ActionName]/[Parameters]`

    Když přidáte výše uvedeném fragmentu kódu, oznamujete aplikaci výchozí nastavení `HelloWorld` řadiče a `Index` metody akce.

6. Přidat `services.AddMvc();` volat na `ConfigureServices` metoda, jak je uvedeno dále:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
    }
    ```

    Informace o parametrech můžete předat také z adresy URL k řadiči.

7. Přidejte do vaší HelloWorldController jinou metodu, jak je uvedeno dále:

    ```csharp
    public string Xamarin(string name)
    {
        return HtmlEncoder.Default.Encode($"Hello {name}, welcome to Visual Studio for Mac");
    }
    ```

8. Pokud teď ke spuštění aplikace, by měl automaticky otevře prohlížeč:

    ![Spuštěné aplikaci v prohlížeči](media/asp-net-core-image13.png)

9. Procházení k `http://localhost:xxxx/HelloWorld/Xamarin?name=Amy` (nahrazení `xxxx` s správný port), měli byste vidět následující:

    ![Spuštěné aplikaci v prohlížeči bez argumentů](media/asp-net-core-image10.png)


## <a name="troubleshooting"></a>Poradce při potížích

Pokud potřebujete nainstalovat .NET Core ručně na Mac OS 10.11 (El Capitan) a vyšší, postupujte takto:

1. Před zahájením instalace .NET Core, ujistěte se, že jste aktualizovali všechny aktualizace operačního systému na nejnovější stabilní verze. Zkontrolovat to můžete tak, že přejdete do aplikace obchod a vyberete kartu aktualizace.

2. Postupujte podle kroků uvedených na [.NET Core lokality](https://www.microsoft.com/net/core#macos).

Ujistěte se, že všechny čtyři provést postup uvedený úspěšně zkontrolujte, zda je úspěšně nainstalován .NET Core.

## <a name="summary"></a>Souhrn

Tento průvodce vám Dal Úvod do ASP.NET Core. Popisuje, co je, kdy použít a poskytuje informace o používání v sadě Visual Studio for Mac.
Další informace o dalších krocích zde naleznete následující příručky:
- [ASP.NET Core](https://docs.microsoft.com/aspnet/core/#build-web-ui-and-web-apis-using-aspnet-core-mvc) dokumentace.
- [Vytváření služeb back-end pro nativních aplikací Mobile](https://docs.microsoft.com/aspnet/core/mobile/native-mobile-backend), který ukazuje vytvoření služby REST pro aplikace na platformě Xamarin.Forms pomocí ASP.NET Core.
- [ASP.NET Core praktické cvičení](https://github.com/Microsoft/vs4mac-labs/tree/master/Web/Getting-Started).

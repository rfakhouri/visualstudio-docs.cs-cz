---
title: 'Krok 3: Práce s daty v aplikaci ASP.NET Core'
description: Začněte pracovat s daty s použitím Entity Framework Core ve webové aplikaci ASP.NET Core s touto Výukové video a podrobné pokyny.
ms.custom: get-started
ms.date: 03/31/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
monikerRange: vs-2019
ms.topic: tutorial
ms.devlang: CSharp
author: ardalis
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: c1d95d7621a97a36fdf737e7d3dd4f8baf713645
ms.sourcegitcommit: b6177ce198c7c5a00030604c9d4faa735405d5df
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/04/2019
ms.locfileid: "59018178"
---
# <a name="step-3-work-with-data-using-entity-framework"></a>Krok 3: Práce s daty pomocí Entity Frameworku

Postupujte podle těchto kroků můžete začít pracovat s daty s použitím Entity Framework Core ve webové aplikaci ASP.NET Core.

_Podívejte se na video a postupovat s námi můžete přidat do vaší první aplikace ASP.NET Core._

> [!VIDEO https://www.youtube.com/embed/dulJCwNrqhM]

## <a name="open-your-project"></a>Otevřete svůj projekt

Pokud jste postupovali společně s Tato videa, otevřete projekt webové aplikace, kterou jste vytvořili v předchozí části. Pokud začínáte sem, budete muset vytvořit nový projekt a zvolte **webová aplikace ASP.NET** a potom **webovou aplikaci**. Zbývající možnosti ponechte výchozí hodnoty.

## <a name="add-your-model"></a>Přidání modelu

První věc, kterou potřebujete pro práci s daty v aplikaci ASP.NET Core je popisují, jak by měla vypadat data. Říkáme, že vytváření *modelu* věcí součástí Snažili jsme se to vyřešit problém. V reálných aplikacích přidáme vlastní obchodní logiky do těchto modelů proto můžou chovat určitými způsoby a automatizaci úloh pro nás. V tomto příkladu chceme vytvořit jednoduchý systém pro sledování Deskové hry. Potřebujeme třídu, která představuje hru a zahrnuje některé vlastnosti, které chceme záznam o tuto hru, například kolik hráčů může podporovat. Tato třída přejde do nové složky v kořenové složce webového projektu, volá se, vytvoříme *modely*.

```csharp
public class Game
{
    public int Id { get; set; }
    public string Title { get; set; }
    public int PublicationYear { get; set; }
    public int MinimumPlayers { get; set; }
    public int MaximumPlayers { get; set; }
}
```

## <a name="create-the-pages-to-manage-your-game-library"></a>Vytváření stránek pro správu vaší herní knihovnu

Nyní jsme připraveni vytvořit stránky, které nám budete používat ke správě naší knihovně hry. To může být zvukové složitý, ale je ve skutečnosti neuvěřitelně jednoduché. Nejdřív potřebujeme rozhodnout, kde v naší aplikaci by měly existovat tuto funkci. Otevřete složku stránky ve webovém projektu a přidejte novou složku. Pojmenujte ji *hry*.

Teď klikněte pravým tlačítkem na hry a zvolte **přidat** > **novou vygenerovanou položku**. Zvolte pro stránky Razor pomocí **Entity Frameworku (CRUD)** možnost. Zastupuje CRUD "Vytvoření, čtení, aktualizace nebo odstranění" a tato šablona vytvoří stránky pro každou z těchto operací (včetně stránku "seznam všech" a "zobrazte podrobnosti o jednu položku" stránku).

![Visual Studio. 2019 ASP.NET Core přidat vygenerované stránky](media/vs-2019/vs2019-add-scaffold.png)

Vyberte třídu her modelu a přidání nové třídy kontextu dat pomocí ikony '+'. Pojmenujte ji `AppDbContext`. Zbývající pole ponechte jako výchozí hodnoty a klikněte na tlačítko **přidat**.

Zobrazí se že následující stránky Razor přidán do složky Hry:

- Create.cshtml
- Delete.cshtml
- Details.cshtml
- Edit.cshtml
- Index.cshtml

![Visual Studio. 2019 ASP.NET Core, automaticky generovaný stránky](media/vs-2019/vs2019-scaffolded-pages.png)

Kromě přidání stránky *hry* složky, operace generování uživatelského rozhraní přidáním kódu Moje *Startup.cs* třídy. Hledání `ConfigureServices` metody této třídy, zobrazí se přidal tento kód:

```csharp
services.AddDbContext<AppDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("AppDbContext")));
```

Naleznete zde také `AppDbContext` připojovací řetězec je přidaný do projektu *appsettings.json* souboru.

Pokud nyní spustíte aplikaci, se může selhat, protože žádná databáze. zatím se nevytvořilo. Můžete nakonfigurovat aplikaci automaticky vytvářet databáze v případě potřeby podle [přidáte nějaký kód do souboru Program.cs](/aspnet/core/data/ef-rp/intro?view=aspnetcore-2.1&tabs=visual-studio#update-main):

```csharp
public static void Main(string[] args)
{
    var host = CreateWebHostBuilder(args).Build();

    using (var scope = host.Services.CreateScope())
    {
        var services = scope.ServiceProvider;

        try
        {
            var context = services.GetRequiredService<SchoolContext>();
            context.Database.EnsureCreated();
        }
        catch (Exception ex)
        {
            var logger = services.GetRequiredService<ILogger<Program>>();
            logger.LogError(ex, "An error occurred creating the DB.");
        }
    }

    host.Run();
}
```

Většina kódu je jen pro zpracování chyb a k zajištění přístupu k EF Core `AppDbContext` předtím, než je aplikace spuštěna. Důležité řádek je ten, který říká `context.Database.EnsureCreated()`, pokud ještě neexistuje. Tím se vytvoří databáze. Aplikace je nyní připraven ke spuštění.

## <a name="test-it-out"></a>Otestování

Spusťte aplikaci a přejděte do `/Games` do adresního řádku. Zobrazí se stránka prázdným seznamem. Klikněte na tlačítko **vytvořit nový** přidáte nový `Game` do kolekce. Vyplňte formulář a klikněte na tlačítko **vytvořit**. Měli byste vidět v zobrazení seznamu. Klikněte na **podrobnosti** zobrazíte podrobnosti o jeden záznam.

Přidáte jiný záznam. Můžete kliknout na *upravit* změnit podrobnosti o záznamu, nebo **odstranit** odebrat, který vás vyzve k potvrzení před skutečně odstraní záznam.

![Visual Studio. 2019 ASP.NET Core, automaticky generovaný stránky v prohlížeči](media/vs-2019/vs2019-game-list.png)

To je všechno, co trvalo začít pracovat s daty v aplikaci ASP.NET Core pomocí EF Core a Visual Studio 2019.

## <a name="next-steps"></a>Další kroky

V dalším videu se dozvíte, jak přidat podporu pro webové rozhraní API do vaší aplikace.

[Krok 4: Vystavení webového rozhraní API z vaše aplikace ASP.NET Core](tutorial-aspnet-core-ef-step-04.md)

## <a name="see-also"></a>Viz také:

- [Stránky Razor pomocí Entity Framework Core v ASP.NET Core](/aspnet/core/data/ef-rp/intro?view=aspnetcore-2.1&tabs=visual-studio)
- [ASP.NET Core Razor Pages s EF Core](/aspnet/core/data/?view=aspnetcore-2.1)

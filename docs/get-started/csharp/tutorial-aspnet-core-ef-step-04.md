---
title: 'Krok 4: Vystavení webového rozhraní API z vaše aplikace ASP.NET Core'
description: Přidání webového rozhraní API do webové aplikace ASP.NET Core s touto Výukové video a podrobné pokyny.
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
ms.openlocfilehash: 93e3b0af04060c3a3805b29e5d1da71c4f60ec31
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "59018087"
---
# <a name="step-4-expose-a-web-api-from-your-aspnet-core-app"></a>Krok 4: Vystavení webového rozhraní API z aplikace ASP.NET Core

Postupujte podle těchto kroků přidejte webového rozhraní API do stávající aplikace ASP.NET Core.

_Podívejte se na video a můžete pokračovat k přidání podpory webového rozhraní API do vaší první aplikace ASP.NET Core._

> [!VIDEO https://www.youtube.com/embed/o_fYPOsAXts]

## <a name="open-your-project"></a>Otevřete svůj projekt

Otevřete aplikaci ASP.NET Core v aplikaci Visual Studio 2019. Aplikace by již být pomocí EF Core ke správě vašich typů modelu podle konfigurace v [kroku 3 v této sérii kurzů](tutorial-aspnet-core-ef-step-03.md).

## <a name="add-an-api-controller"></a>Přidat kontroler API

Klikněte pravým tlačítkem na projekt a přidejte novou složku s názvem *Api*. Potom klikněte pravým tlačítkem na tuto složku a zvolte **přidat** > **novou vygenerovanou položku**. Zvolte **kontroler API s akcemi používající nástroj Entity Framework.** Teď zvolte existující třídy modelu a klikněte na tlačítko **přidat**.

![Visual Studio. 2019 ASP.NET Core, automaticky generovaný kontroler API](media/vs-2019/vs2019-add-scaffold-api.png)

## <a name="reviewing-the-generated-controller"></a>Kontrola vytvořeném kontroleru

Generovaný kód obsahuje novou třídu kontroleru. V horní části definice třídy jsou dva atributy.

```csharp
[Route("api/[controller]")]
[ApiController]
public class GamesController : ControllerBase
```

První z nich určuje trasu pro akce v tomto kontroleru jako `api/[controller]` to znamená, že pokud je název kontroleru `GamesController` trasy bude `api/Games`.

Druhý atribut `[ApiController]`, některé užitečné ověření přidá do třídy, jako je zajištění každá akce, metoda obsahuje vlastní `[Route]` atribut.

```csharp
public class GamesController : ControllerBase
{
    private readonly AppDbContext _context;

    public GamesController(AppDbContext context)
    {
        _context = context;
    }
```

Kontroler používá stávající `AppDbContext`, předaná do konstruktoru. Každá akce bude toto pole použít pro práci s daty vaší aplikace.

```csharp
// GET: api/Games
[HttpGet]
public IEnumerable<Game> GetGame()
{
    return _context.Game;
}
```

Prvním způsobem je jako zadaný pomocí jednoduchého požadavek GET `[HttpGet]` atribut. Nepřijímá žádné parametry a vrátí seznam všech her v databázi.

```csharp
// GET: api/Games/5
[HttpGet("{id}")]
public async Task<IActionResult> GetGame([FromRoute] int id)
{
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }

    var game = await _context.Game.FindAsync(id);

    if (game == null)
    {
        return NotFound();
    }

    return Ok(game);
}
```

Určuje další metoda `{id}` v trase, které se přidají do následující trasy `/` tak úplnou směrování bude vypadat `api/Games/5` jak je znázorněno v komentáři v horní části. `id` Vstup je namapována na `id` parametr metody. Uvnitř metody, pokud model není platný `BadRequest` vrátí výsledek. V opačném případě se pokusí EF najít záznam odpovídající zadané `id`. V případě nedostupnosti `NotFound` se vrátí výsledek, jinak odpovídající `Game` vrátí záznam.

```csharp
// PUT: api/Games/5
[HttpPut("{id}")]
public async Task<IActionResult> PutGame([FromRoute] int id, [FromBody] Game game)
{
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }

    if (id != game.Id)
    {
        return BadRequest();
    }

    _context.Entry(game).State = EntityState.Modified;

    try
    {
        await _context.SaveChangesAsync();
    }
    catch (DbUpdateConcurrencyException)
    {
        if (!GameExists(id))
        {
            return NotFound();
        }
        else
        {
            throw;
        }
    }

    return NoContent();
}
```

Další `[HttpPut]` požadavku na rozhraní API se používá k provedení aktualizace. Nové `Game` záznamu je k dispozici v textu požadavku. Některá ověřování a kontroly chyb provádí, a pokud vše, co je úspěšné aktualizaci záznamu v databázi s hodnotami v textu požadavku. Jinak se vrátí odpovídající chybové odpovědi.

```csharp
// POST: api/Games
[HttpPost]
public async Task<IActionResult> PostGame([FromBody] Game game)
{
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }

    _context.Game.Add(game);
    await _context.SaveChangesAsync();

    return CreatedAtAction("GetGame", new { id = game.Id }, game);
}
```

`[HttpPost]` Požadavku se používá k přidání nových záznamů do systému. Stejně jako u `[HttpPut]`, se přidá tento záznam v textu požadavku. Pokud je platný, EF Core přidá záznam do databáze a akce vrátí aktualizovaný záznam (s jeho databáze, vygeneruje ID) a odkaz na záznam v rozhraní API.

```csharp
// DELETE: api/Games/5
[HttpDelete("{id}")]
public async Task<IActionResult> DeleteGame([FromRoute] int id)
{
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }

    var game = await _context.Game.FindAsync(id);
    if (game == null)
    {
        return NotFound();
    }

    _context.Game.Remove(game);
    await _context.SaveChangesAsync();

    return Ok(game);
}
```

A konečně `[HttpDelete]` trasy s ID slouží k odstranění záznamu. Pokud je požadavek platný a existuje záznam se zadaným ID., EF Core ho odstranit z databáze.

## <a name="adding-swagger"></a>Přidání Swagger

Swagger je dokumentace k rozhraní API a testovací nástroj, který se dá přidat jako sadu služeb a middleware pro aplikace ASP.NET Core. Chcete-li to provést, klikněte pravým tlačítkem na projekt a zvolte **spravovat balíčky NuGet**. Klikněte na **Procházet** a vyhledejte `Swashbuckle.AspNetCore` a nainstalovat odpovídající balíček.

![Visual Studio 2019 přidat z Nuget Swashbuckle](media/vs-2019/vs2019-nuget-swashbuckle.png)

Po instalaci otevřete `Startup.cs` a přidejte následující na konec objektu `ConfigureServices` metody:

```csharp
services.AddSwaggerGen(c =>
{
    c.SwaggerDoc("v1", new Info { Title = "My API", Version = "v1" });
});
```

Také budete muset přidat `using Swashbuckle.AspNetCore.Swagger;` v horní části souboru.

V dalším kroku přidejte následující text do `Configure` metoda, těsně před `UseMvc`:

```csharp
// Enable middleware to serve generated Swagger as a JSON endpoint.
app.UseSwagger();

// Enable middleware to serve swagger-ui (HTML, JS, CSS, etc.), 
// specifying the Swagger JSON endpoint.
app.UseSwaggerUI(c =>
{
    c.SwaggerEndpoint("/swagger/v1/swagger.json", "My API V1");
});
```

Teď byste měli moct sestavit a spustit aplikaci. V prohlížeči přejděte na `/swagger` do adresního řádku. Zobrazí se seznam koncových bodů rozhraní API vaší aplikace a modely. 

![Visual Studio. 2019 Swagger stránku v prohlížeči](media/vs-2019/vs2019-swagger-browser.png)

Klikněte na koncový bod v rámci her, pak `Try it out` a `Execute` zobrazíte chování různých koncových bodů.

## <a name="next-steps"></a>Další kroky

V dalším videu se dozvíte, jak nasadit aplikaci do Azure.

[Krok 5: Nasazení aplikace ASP.NET Core do Azure](tutorial-aspnet-core-ef-step-05.md)

## <a name="see-also"></a>Viz také:

- [Začínáme se službou Swashbuckle a ASP.NET Core](/aspnet/core/tutorials/getting-started-with-swashbuckle?view=aspnetcore-2.2&tabs=visual-studio)
- [ASP.NET Core webové rozhraní API nápovědy stránky ve Swaggeru / OpenAPI](/aspnet/core/tutorials/web-api-help-pages-using-swagger?view=aspnetcore-2.2)
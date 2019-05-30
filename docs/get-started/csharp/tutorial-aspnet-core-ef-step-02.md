---
title: 'Krok 2: Vytvoření vaší první webové aplikace ASP.NET Core'
description: Vytvoření vaší první webové aplikace ASP.NET Core s touto Výukové video a podrobné pokyny.
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
ms.openlocfilehash: 740d6336ab4258d3111dd6708de859108e22365e
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402070"
---
# <a name="step-2-create-your-first-aspnet-core-web-app"></a>Krok 2: Vytvoření vaší první webové aplikace ASP.NET Core

Vytvoření vaší první webové aplikace ASP.NET Core s touto Výukové video a podrobné pokyny.

_Podívejte se na toto video a použijte k vytvoření první aplikace ASP.NET Core._

> [!VIDEO https://www.youtube.com/embed/-79RkpyFB6E]

## <a name="start-visual-studio-2019-and-create-a-new-project"></a>Spusťte Visual Studio 2019 a vytvořte nový projekt

Spusťte Visual Studio 2019 a klikněte na **vytvořit nový projekt**. Zvolte **webová aplikace ASP.NET Core**. Zvolte **webovou aplikaci** šablony a ponechat výchozí název a umístění projektu. Klikněte na možnost **Vytvořit**. Podrobnější pokyny o [předchozí videa v této řadě kurzů](tutorial-aspnet-core-ef-step-01.md).

![Visual Studio 2019 Choose ASP.NET Core Project Options](media/vs-2019/vs2019-choose-aspnetcore-project.png)

## <a name="explore-the-new-project"></a>Prozkoumejte nový projekt

V okně Průzkumník řešení na pravé straně se zobrazí obsah nový projekt. Jsou popsány zde.

![Visual Studio 2019 ASP.NET Core Project](media/vs-2019/vs2019-solution-explorer.png)

### <a name="wwwroot"></a>wwwroot

*Wwwroot* složky obsahuje statické soubory, které budou veřejně přístupná z webové aplikace. Obvykle obsahuje šablony stylů, soubory skriptů na straně klienta a obrázků.

### <a name="pages"></a>Stránky

*Stránky* složky obsahuje stránky Razor. Výchozí šablona nabízí několik stránek, včetně *Index.cshtml* stránku, která je domovskou stránku aplikace, stejně jako informace o, kontaktů a tak dále.

### <a name="appsettingsjson"></a>appsettings.json

Tento soubor obsahuje nastavení konfigurace pro webový server ve formátu JSON.

### <a name="programcs"></a>Program.cs

Tento soubor slouží jako vstupní bod pro aplikaci. Při spuštění aplikace, je jeho metodu Main první metodu, která se spustí a je zodpovědný za vytváření webového hostitele, který bude obsahovat aplikaci.

### <a name="startupcs"></a>Startup.cs

Vytvoření webového hostitele v *Program.cs* odkazuje na třídu pro spuštění a volání metody konfigurace aplikace. Metoda ConfigureServices je zodpovědný za nastavení služby, které aplikace bude používat. `Configure` Metoda nastaví kanál požadavků HTTP aplikaci. Každý požadavek prochází tímto kanálem interakci s každého jednotlivého *middleware* jako je spuštění provedeno.

### <a name="indexcshtml"></a>Index.cshtml

Domovská stránka pro web obsahuje některé kódu HTML a kódu Razor na straně serveru. Používá pro určení modelu stránky Razor `IndexModel`, která je umístěná v přidruženém *Index.cshtml.cs* souboru. Nastavením hodnoty ve slovníku ViewData také nastaví nadpis stránky. Tato hodnota slovníku ViewData je určen pro čtení  *\_Layout.cshtml* soubor umístěný ve složce sdílené ve složce stránky. Soubor rozložení sdílí mnoho stránek Razor a poskytuje běžné vzhledu a chování aplikace. Každá stránka obsahu se vykreslí v kódu HTML soubor rozložení.

## <a name="run-the-application"></a>Spuštění aplikace

Nyní spusťte aplikaci a zobrazit v prohlížeči. Můžete spustit aplikace pomocí **Ctrl**+**F5** nebo výběrem **ladění** > **spustit bez ladění**z nabídky sady Visual Studio.

## <a name="customize-the-application"></a>Přizpůsobení aplikace

Přidat vlastnost, která má *Index.cshtml.cs* souborů a nastavení jeho hodnoty na aktuální čas v `OnGet` obslužné rutiny:

```csharp
public string Time { get; set; }
public void OnGet()
{
    Time = DateTime.Today.ToShortTimeString();
}
```

Nahradit `<div>` obsahu v *Index.cshtml* se tento kód:

```cshtml
<h2>It's @Model.Time right now on the server!</h2>
```

Spusťte aplikaci znovu. Měli byste vidět, že na stránce se nyní zobrazí aktuální čas, ale je vždy půlnoc! To není správné.

![Projekt Visual Studio. 2019 ASP.NET Core v prohlížeči](media/vs-2019/vs2019-app-in-browser.png)

## <a name="debug-the-application"></a>Ladění aplikace

Přidejte zarážku na `OnGet` metody, kde jsme už přiřazení hodnoty k `Time` a čas spusťte ladění aplikace.

Zastaví provádění na řádku kde můžete vidět, že `DateTime.Today` obsahuje data, ale čas je vždy půlnoc protože neobsahuje časové údaje. 

![Projekt Visual Studio. 2019 ASP.NET Core v prohlížeči](media/vs-2019/vs2019-breakpoint.png)

Změňte ji na použití `DateTime.Now` a pokračovat v provádění. Nový kód pro `OnGet` by měl být:

```csharp
public void OnGet()
{
    Time = DateTime.Now.ToShortTimeString();
}
```

Teď byste měli vidět skutečný čas v prohlížeči přejdete na aplikaci.

> [!NOTE]
> Výstup může lišit od bitovou kopii, protože výstupní formát ToShortDateTimeString závisí na nastavení aktuální jazykové verze. Viz <xref:System.DateTime.ToShortTimeString>.

![Projekt Visual Studio. 2019 ASP.NET Core v prohlížeči](media/vs-2019/vs2019-app-fixed-in-browser.png)

## <a name="next-steps"></a>Další kroky

V dalším videu se dozvíte, jak přidat podporu pro data do vaší aplikace.

[Kurz: Práce s daty v aplikaci ASP.NET Core](tutorial-aspnet-core-ef-step-03.md)

## <a name="see-also"></a>Viz také:

- [Kurz: Vytvoření webové aplikace stránky Razor pomocí ASP.NET Core](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)

---
title: Razor
description: Informace o podpoře Razor v aplikacích asp.net Core v Visual Studio pro Mac
author: sayedihashimi
ms.author: sayedha
ms.date: 05/03/2018
ms.technology: vs-ide-general
ms.assetid: F898CB6E-05ED-44CD-8DB6-427B2592CCC6
ms.openlocfilehash: a66a31d2c63fcb0e2adc4554c49a76c727f9a288
ms.sourcegitcommit: cf8c0fef2b9690595e99ce3802586cdd55fd37c2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107948"
---
# <a name="razor"></a>Razor

Visual Studio pro Mac poskytuje podporu pro úpravy Razor, včetně IntelliSense a zvýrazňování syntaxe v souborech *. cshtml* .

![Úpravy Razor v Visual Studio pro Mac](media/razor-editor.png)

Tato příručka poskytuje Úvod k vytvoření první webové aplikace Razor. Podrobnější návod najdete v [dokumentaci k rozhraní .NET Core v Razor Pages](/aspnet/core/razor-pages/index).

## <a name="creating-a-new-razor-project"></a>Vytvoření nového projektu Razor

* Na úvodní obrazovce vyberte **Nový** a vytvořte nový projekt:

![Visual Studio pro Mac nový projekt](media/razor-new.png)

* V dialogovém okně Nový projekt přejděte na**Webová aplikace** **.NET Core** > **App** > a vyberte tlačítko **Další** :

![Šablona projektu Razor](media/razor-new-project1.png)

* Vyberte požadované cílové rozhraní .NET Core (doporučeno 2,2 nebo vyšší) a vyberte **Další**.  Vyberte název projektu a v případě potřeby přidejte podporu Gitu. Vyberte **vytvořit** a vytvořte projekt.

![Název projektu Razor](media/razor-new-project2.png)

Visual Studio pro Mac otevře projekt v rozložení kódu.

* Spustit projekt bez ladění pomocí **příkazu cmd-opt-F5**

Visual Studio se spustí [kestral](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel) a spustí se prohlížeč a `https://localhost:5001` zobrazí se vaše první webová aplikace Razor:

![Webová aplikace Razor v Safari](media/razor-webapp.png)

## <a name="project-anatomy"></a>Anatomie projektu

Webové aplikace Razor se skládají z následujících součástí:

### <a name="pages-folder"></a>Složka stránky

Složka stránky v rámci projektu je místo, kde lze najít webové stránky společně s kódem na pozadí pro každý z nich:
* Soubor * *. cshtml* pro značky HTML a syntaxe Razor.
* Soubor * *. cshtml.cs* pro C# kód na pozadí pro zpracování událostí stránky.

Podpůrné soubory mají názvy začínající podtržítkem. Například soubor _Layout. cshtml nakonfiguruje prvky uživatelského rozhraní společné pro všechny stránky. Tento soubor nastaví navigační nabídku v horní části stránky a oznámení o autorských právech v dolní části stránky. Další informace najdete v tématu [rozložení v ASP.NET Core](https://docs.microsoft.com/aspnet/core/mvc/views/layout).

### <a name="launch-settings"></a>Nastavení spuštění

Soubor *launchSettings. JSON* obsahuje nastavení služby IIS, adresu URL aplikace a další související nastavení.

### <a name="app-settings"></a>Nastavení aplikace

Soubor *appSettings, JSON* obsahuje konfigurační data, jako jsou připojovací řetězce.

Další informace o konfiguraci najdete v tématu [konfigurace v průvodci ASP.NET](https://docs.microsoft.com/aspnet/core/fundamentals/configuration/index).

### <a name="wwwroot-folder"></a>Složka wwwroot

Obsahuje statické soubory, jako jsou soubory HTML, JavaScriptové soubory a soubory CSS. Další informace najdete v tématu [statické soubory v ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/static-files).

### <a name="programcs"></a>Program.cs

Obsahuje vstupní bod pro program. Další informace najdete v tématu [ASP.NET Core webového hostitele](https://docs.microsoft.com/aspnet/core/fundamentals/host/web-host).

### <a name="startupcs"></a>Startup.cs

Obsahuje kód, který konfiguruje chování aplikace, například zda vyžaduje souhlas s soubory cookie. Další informace najdete v tématu [spuštění aplikace v ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/startup).

## <a name="see-aso"></a>Viz ASO

Komplexnější průvodce vytvářením webových aplikací Razor najdete [v tématu Úvod do Razor Pages v ASP.NET Core](https://docs.microsoft.com/aspnet/core/razor-pages/index).

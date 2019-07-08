---
title: Razor
description: Informace o podpoře razor na aplikace v asp.net core v sadě Visual Studio pro Mac
author: conceptdev
ms.author: crdun
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: F898CB6E-05ED-44CD-8DB6-427B2592CCC6
ms.openlocfilehash: 181059ae2985f570ad1dc0749045e39ed4ec1e7e
ms.sourcegitcommit: 3cc73e74921a9ceb622542e0e263abeebc455c00
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/08/2019
ms.locfileid: "67624520"
---
# <a name="razor"></a>Razor

Visual Studio pro Mac poskytuje podporu pro Razor úpravy, včetně technologie IntelliSense a zvýrazňování syntaxe ve *.cshtml* soubory.

![Razor editing in Visual Studio for Mac](media/razor-editor.png)

Tato příručka obsahuje úvod do vytváření vaše první webová aplikace Razor. Podrobnější informace najdete [v dokumentaci k .NET Core Razor Pages](/aspnet/core/razor-pages/index).

## <a name="creating-a-new-razor-project"></a>Vytvoření nového projektu Razor

* Na úvodní obrazovce vyberte **nový** k vytvoření nového projektu:

![Visual Studio pro Mac nový projekt](media/razor-new.png)

* V dialogovém okně Nový projekt, přejděte na **.NET Core** > **aplikace** > **webovou aplikaci** a vyberte **Další**tlačítka:

![Šablona projektu Razor](media/razor-new-project1.png)

* Vyberte vaše .NET Core Cílová architektura vyžaduje (doporučeno 2.2 nebo vyšší) a vyberte **Další**.  Zvolte název pro váš projekt a přidat podporu úložiště git, pokud je to nutné. Vyberte **vytvořit** pro vytvoření projektu.

![Název projektu Razor](media/razor-new-project2.png)

Visual Studio pro Mac se otevře projekt v rozložení kódu.

* Spuštění projektu bez ladění pomocí **Cmd optimalizované F5**

Visual Studio spustí [Kestral](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel) a spustit prohlížeč pro `https://localhost:5001` a zobrazit vaše první webová aplikace Razor:

![Webová aplikace Razor v Safari](media/razor-webapp.png)

## <a name="project-anatomy"></a>Anatomie projektu

Razor webové aplikace se skládá z následujících součástí:

### <a name="pages-folder"></a>Složka stránek

Složka stránek v rámci projektu je, kde lze nalézt webové stránky, spolu s kódu pro každé:
*    A * *.cshtml* soubor pro kód HTML a syntaxe Razor.
*    A * *. cshtml.cs* soubor pro vaše C# kódu pro zpracování událostí stránky.

Podpůrné soubory mají názvy, které začínají znakem podtržítka. Například soubor _Layout.cshtml nastaví prvky uživatelského rozhraní, které jsou společné pro všechny stránky. Tento soubor nastaví navigační nabídce v horní části stránky a o autorských právech v dolní části stránky. Další informace najdete v tématu [rozložení v ASP.NET Core](https://docs.microsoft.com/aspnet/core/mvc/views/layout).

### <a name="launch-settings"></a>Nastavení spuštění

*LaunchSettings.json* soubor obsahuje nastavení služby IIS, adresa URL aplikace a další související nastavení.

### <a name="app-settings"></a>Nastavení aplikace

*AppSettings json* soubor obsahuje konfigurační data, jako je například připojovací řetězce.

Další informace o konfiguraci najdete v článku [konfigurace do Průvodce pro technologii ASP.NET](https://docs.microsoft.com/aspnet/core/fundamentals/configuration/index).

### <a name="wwwroot-folder"></a>složku Wwwroot

Obsahuje statické soubory, jako jsou soubory HTML, soubory jazyka JavaScript a soubory šablon stylů CSS. Další informace najdete v tématu [statických souborů v ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/static-files).

### <a name="programcs"></a>Program.cs

Obsahuje vstupní bod programu. Další informace najdete v tématu [webového hostitele ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/host/web-host).

### <a name="startupcs"></a>Startup.cs

Obsahuje kód, který nakonfiguruje chování aplikace, jako je například jestli vyžaduje souhlas pro soubory cookie. Další informace najdete v tématu [spuštění aplikace v ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/startup).

## <a name="see-aso"></a>Zobrazit aso

Více komplexní pokyny týkající se vytvoření Razor webových aplikací najdete v části [Úvod do služby v ASP.NET Core Razor Pages](https://docs.microsoft.com/aspnet/core/razor-pages/index).

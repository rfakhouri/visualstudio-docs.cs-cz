---
title: "Výhody sady Visual Studio pro Mac přes Xamarin Studio | Microsoft Docs"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 6ACF5FD4-D5C1-4050-95E3-467C753F25F1
ms.openlocfilehash: 08e693e92d6d07da21f8230f9c1de49f071c05e5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="benefits-of-visual-studio-for-mac-over-xamarin-studio"></a>Výhody sady Visual Studio pro Mac přes Xamarin Studio 
 
Visual Studio pro Mac nahradili Xamarin Studio jako plné IDE na macu. Poskytuje funkce, které vám umožní vyvíjet webové aplikace a služby, mobilních a desktopových aplikací pro různé platformy a hry. Kromě toho umožňuje integraci s Azure uloženy, jestli to znamená publikování v Azure nebo vytváření Azure Functions. Obsahuje všechny objekty, které očekáváte od moderní IDE, včetně editoru plné zdroje, výkonné ladicí program, přizpůsobitelné pracovní prostor, integrace gitu a bohaté rozšíření systému, navržená nativně pro Mac. 

Mezi další funkce patří: 

* Na základě Roslyn C# technologii IntelliSense, refaktoring analyzátory a opravy kódu 
* Správy na základě NuGet balíčků 
* Formát kompatibilní projekt Visual Studio 
* Modul sestavení nástroje MSBuild 
* Integrované testování částí 
* Podpora pro F # out-of-the-box 

Výhody uvedené v této příručce, která jsou označena jako **Preview** jsou dostupné jenom [alfa kanálu](https://docs.microsoft.com/visualstudio/mac/update#Changing_the_Updater_channel). 

## <a name="language-support"></a>Jazyková podpora 

Psaní kódu jazyka C# 7 v počítači Mac se nabízí pouze v sadě Visual Studio for Mac.

## <a name="net-core"></a>.NET Core  

[.NET Core](https://www.microsoft.com/net/core#macos) je platforma pro vytváření aplikací, které běží na Windows, Linuxu a Macu. Visual Studio for Mac podporuje načítání, vytváření, používání a ladění projektů .NET Core. 

.NET core je nainstalován pomocí sady Visual Studio pro Mac a funguje mimo pole.

Podpora .NET Core zahrnuje: 

* C# a F# IntelliSense 
* Šablony projektu .NET Core pro konzolu, knihovnu a webové aplikace 
* Úplnou podporu ladění, včetně zarážek, zásobníku volání, okna kukátka a dalších funkcí 
* Odkazy na balíček NuGet a na základě MSBuild obnovení. 
* Testování podporu pro spouštění a ladění testy s Visual Studio platforma testu, která je součástí rozhraní .NET Core SDK integrované částí. 
* Migrace ze starý formát souboru project.json. 
* Podpora v rozhraní .NET standardní projektu.

## <a name="web-development"></a>Vývoj webů  

### <a name="aspnet-core"></a>Jádro ASP.NET 

Visual Studio pro Mac zahrnuje ASP.NET Core šablon pro projekty MVC a webového rozhraní API z pole.
 
![HTML Intellisense](media/benefits-vsmac-over-xs-image3.png)

Visual Studio pro Mac také přidá nový web Podpora nástrojů pro soubory HTML, CSS a JSON. 

### <a name="html"></a>HTML 

* Nová šablona HTML 
* Vylepšené inteligentní odsazení a formátování 
* Vylepšené barevné zvýrazňování 
* Vylepšená technologie IntelliSense 
* Sbalování kódu (je třeba ho povolit) 
* Příkaz pro zrušení minifikace 
* Vylepšené šablony kódu (fragmenty kódu) 
* Obklopení výběru pomocí `<div>` 
* Možnost přesunutí vybraného textu nahoru a dolů 

### <a name="css"></a>CSS 

* Vylepšené inteligentní odsazení a formátování 
* Vylepšené barevné zvýrazňování 
* Vylepšená technologie IntelliSense 
* Sbalování kódu 
* Mnoho šablon kódu (fragmentů kódu) 
* Možnost přesunutí vybraného textu nahoru a dolů 

### <a name="json"></a>FORMÁT JSON 
* Výběr schématu s přístupem k schemastore.org 
* Ověřování ze schématu 
* IntelliSense ze schématu 
* Vylepšené inteligentní odsazení a formátování 
* Vylepšené barevné zvýrazňování 
* Přidávání komentářů a jejich rušení 
* Vkládání uvozovek a párování závorek 
* Možnost přesunutí vybraného textu nahoru a dolů 

## <a name="publishing-to-azure"></a>Publikování do služby Azure

Pomocí sady Visual Studio pro Mac je možné publikovat ASP.NET Core webové aplikace a služby Azure App Service. 

![Publikování v Azure](media/benefits-vsmac-over-xs-image1.png)

### <a name="azure-functions-preview"></a>Azure Functions (**Preview**)

Azure Functions je řešení umožňující snadno spouštět malé části kódu, nebo funkcí, v cloudu. Visual Studio pro Mac můžete kód a místně ladění Azure Functions. Chcete-li získat v dialogu Nový projekt spustit, podívejte se na Azure Functions v cloudu. 

### <a name="docker-support-preview"></a>Podpora docker (**Preview**)

Teď můžete publikovat aplikace ASP.NET Core Docker kontejnery a spustit z Azure App Service. 

Chcete-li povolit podporu Docker ve vašem projektu, klikněte pravým tlačítkem na vaší webové aplikace ASP.NET Core a vyberte **Přidat > přidat podporu Docker**. 

K publikování webové aplikace na kontejner Docker, použít **publikovat > Publikovat do Azure** pracovního postupu zavedená v sadě Visual Studio for Mac.

## <a name="source-editor-improvements"></a>Vylepšení editoru zdrojového kódu 

Kromě na základě Roslyn C# technologii IntelliSense, refaktoring, analyzátory a opravy kódu sady Visual Studio pro Mac zdroj editor obsahuje následující vylepšení přes Xamarin Studio: 

### <a name="language-bundles"></a>Jazykové sady 

Visual Studio pro Mac se podpora pro TextMate (`.tmBundle`) a sublime 3 (`.sublime`) jazyk sad, které můžete použít pro přidání: 

* Editor barevné motivy 
* Fragmenty kódu 
* Gramatika pro nové jazyky, povolení zvýraznění a basic IntelliSense 

Můžete přidat tyto sady v **Předvolby > textový Editor > jazykové sady**. 

### <a name="color-theme-support"></a>Barva motivu podpory 

Následující formáty motivu barvu jsou podporovány v sadě Visual Studio pro Mac: 

* Visual Studio (`.vssettings`) 
* Xamarin studio (`.json`) 
* TextMate (`tmTheme`) 

## <a name="unity"></a>Unity 

[Unity](https://unity3d.com/) je nástroj herní vytvoření můžete použít k vytvoření hry 2D a 3D napříč platformami vysoce kvalitní pro hlavní platformy: mobilní telefony, stolních počítačů, konzoly, AR a VR zařízení a to i na webu. 

Počínaje Unity 5.6.1, můžete použít Visual Studio pro Mac k zápisu a ladění vaše hra Unity. Chcete-li začít, nastavte chcete být 5.6.1 Unity pro Visual Studio editor skriptů. 

Nástroje pro Unity, patří: 

* Podpora skriptů, které jsou napsané v C#. 
* Odsazení Unity řešení. 
* Kliknutím na ladění Unity Editor. 
* IntelliSense pro Unity zprávy. 
* Kód zabarvení pro shadery na Unity. 
* Přístup k dokumentaci Unity. 

## <a name="xamarin"></a>Xamarin 

Při první třídy funkce Xamarin Studio byly vždy funkcí Xamarin a platformy, jsou Xamarin funkce, které jsou dostupné jenom v sadě Visual Studio pro Mac 

### <a name="android"></a>Android 

* [Android SDK manager](https://developer.xamarin.com/guides/android/application_fundamentals/using-the-sdk-manager/)  
* Android O se podporuje jenom v sadě Visual Studio pro Mac, není Xamarin Studio 

### <a name="ios-and-mac"></a>iOS a Mac 

* [Aktualizace pracovního postupu podpisový iOS](https://developer.xamarin.com/guides/cross-platform/macios/apple-account-management/) 
    * Vytvoření podpisového identit a instalují je do místní řetězce klíčů. 
    * Vytvořte profily zřizování. 
    * Přidejte do stávající profil podpisové identity.
    *  Zřízení zařízení: registrace zařízení v portálu pro vývojáře Apple a přidat je do profilu pro zřizování.
* iOS 11, watchOS 4 a tvOS 2 budou pouze podporované v sadě Visual Studio pro Mac, není Xamarin Studio 
* Vysoká Sierra systému MacOS se podporuje jenom v sadě Visual Studio pro Mac, není Xamarin Studio 

### <a name="cross-platform"></a>Různé platformy 

* [Xamarin Live Player](https://developer.xamarin.com/guides/cross-platform/live/) (**Preview**) 
* [Xamarin IoT](https://developer.xamarin.com/guides/cross-platform/iot/) (**Preview**) 
 
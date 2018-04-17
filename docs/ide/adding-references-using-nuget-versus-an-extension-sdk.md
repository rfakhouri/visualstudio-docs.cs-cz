---
title: Přidání odkazů pomocí nástroje NuGet a sady Extension SDK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4d4bfd9be5fdcf4544f9bc5c28482cb579af5033
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="adding-references-using-nuget-versus-an-extension-sdk"></a>Přidání odkazů pomocí nástroje NuGet a sady extension SDK

Balíček můžete poskytnout pro používání v rámci projektů sady Visual Studio pomocí buď rozšíření NuGet pro Visual Studio, nebo software development kit (SDK). Prostřednictvím popisu podobnosti a rozdíly mezi dvěma mechanismy, v tomto tématu vám pomohou vybrat tu nejlepší pro úlohu.

- NuGet je systém správy balíčků open source, který slouží ke zjednodušení procesu začlenění knihoven do projektu řešení. Další informace najdete v tématu [NuGet dokumentaci](/nuget).

- Sada SDK je kolekce souborů, které sada Visual Studio zpracuje jako položka jeden odkaz. **Správce odkazů** dialogové okno obsahuje seznam všech sad SDK, které jsou relevantní pro projekt, který je otevřený, když zobrazíte toto okno zobrazené. Když přidáte sady SDK do projektu, je veškerý obsah sady SDK, že přístup pomocí IntelliSense, **sada nástrojů**, návrháře, **Prohlížeč objektů**, MSBuild, nasazení, ladění a zabalení. Další informace o sadách SDK, najdete v tématu [vytváření Software Development Kit](../extensibility/creating-a-software-development-kit.md).

## <a name="which-mechanism-should-i-use"></a>Které mechanismus mám použít?

Následující tabulka vám pomůže porovnat odkazující funkce sady SDK s odkazující funkce NuGet.

|Funkce|Podpora v sadě SDK|Poznámky k sadě SDK|Podpora NuGet|Poznámky k NuGet|
|-------------|-----------------|---------------|-------------------|-----------------|
|Tento mechanismus odkazuje jedna entita a poté jsou dostupné všechny soubory a funkce.|A|Přidat sadu SDK pomocí **správce odkazů** dialogové okno a všechny soubory a funkce jsou k dispozici během pracovní postup vývoje.|A||
|MSBuild automaticky využívá sestavení a metadat Windows (*.winmd*) soubory.|A|V sadě SDK automaticky předáno kompilátoru.|A||
|MSBuild automaticky spotřebuje souborů .h nebo lib.|A|*SDKName.props* soubor informuje Visual Studio, jak nastavit adresář Visual C++ a tak dále, pro automatické *.h* nebo *.lib* souboru spotřeby.|N||
|MSBuild automaticky využívá *.js* nebo *.css* soubory.|A|V **Průzkumníku řešení**, můžete rozbalit uzel odkazu JavaScript SDK a zobrazit jednotlivé *.js* nebo *.css* soubory a pak generovat `<source include/>` značky přetažením Tyto soubory zdrojové soubory. SDK podporuje F5 a automatické balíček instalačního programu.|A||
|MSBuild automaticky přidá ovládacího prvku **sada nástrojů**.|A|**Sada nástrojů** může spotřebovávat sady SDK a zobrazí ovládací prvky v karty, které zadáte.|N||
|Tento mechanismus podporuje instalační program Visual Studio pro rozšíření (VSIX).|A|VSIX má speciální manifest a logiku pro vytvoření balíčků SDK|A|VSIX může být vložen do jiného instalačního programu.|
|**Prohlížeč objektů** zobrazí odkazy.|A|**Prohlížeč objektů** automaticky načte seznam odkazů v sady SDK a jejich výčtu.|N||
|Soubory a odkazy automaticky přidán do **správce odkazů** dialogové okno (odkazy na nápovědu a atd. automaticky naplnit)|A|**Správce odkazů** dialogové okno automaticky zobrazí sady SDK, spolu s odkazy na nápovědu a seznam závislostí sady SDK.|N|NuGet poskytuje svou vlastní **spravovat balíčky NuGet** dialogové okno.|
|Tento mechanismus podporuje víc architektur.|A|Sady SDK se dají dodávat víc konfigurací. MSBuild spotřebuje příslušné soubory pro každý konfigurací projektu.|N||
|Tento mechanismus podporuje různé konfigurace.|A|Sady SDK se dají dodávat víc konfigurací. V závislosti na architektuře projektu nástroje MSBuild spotřebuje příslušné soubory pro každou architekturu projektu.|N||
|Tento mechanismus můžete zadat "nechcete"kopie.|A|V závislosti na tom, jestli jsou soubory vyřadit *\redist* nebo *\designtime* složky, můžete řídit soubory, které chcete zkopírovat do balíčku spotřebitelskou aplikací.|N|Je deklarovat soubory, které chcete kopírovat v manifest balíčku.|
|Zobrazí se obsah ve lokalizované soubory.|A|Lokalizované dokumentů XML v sady SDK budou automaticky zahrnuty návrhu prostředí lépe.|N||
|MSBuild podporuje použití více verzí sady SDK současně.|A|SDK podporuje použití více verzí současně.|N|Není odkazující na. Více než jedna verze souborů NuGet ve vašem projektu nemůže mít současně.|
|Tento mechanismus podporuje příslušné cílové rozhraní, verzí sady Visual Studio a typy projektů.|A|**Správce odkazů** dialogové okno a **sada nástrojů** zobrazit pouze sady SDK, které se vztahují na projekt, tak, aby mohli uživatelé snadněji vybrat odpovídající sady SDK.|Y (částečné)|Pivot je cílové rozhraní. Není žádný filtrování uživatelské rozhraní. V průběhu instalace může vrátit chybu.|
|Tento mechanismus podporuje zadání registrační informace pro nativní WinMDs.|A|Můžete zadat korelace mezi .winmd soubor a soubor DLL v *SDKManifest.xml*.|N||
|Tento mechanismus podporuje zadání závislosti na dalších sadách SDK.|A|Sada SDK pouze upozorní uživatele; Uživatel musí stále nainstalovány a odkazujte na ně ručně.|A|Automaticky; NuGet je vrátí uživatel nebude upozorněn.|
|Tento mechanismus se integruje s [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)] koncepty, jako je například manifest aplikace a ID Framework.|A|Sada SDK musí projít koncepty, které jsou specifické pro [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)] balení a F5 pracovat správně s sady SDK, které jsou k dispozici v[!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)].|N||
|Tento mechanismus se integruje s ladění kanálu pro aplikaci [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace.|A|Sada SDK musí projít [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)]-konkrétní koncepty balení a F5 pracovat správně s sady SDK k dispozici v [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)].|A|Obsah NuGet stane součástí projektu. Je potřeba žádné zvláštní ohledy F5.|
|Tento mechanismus se integruje s manifestů aplikace.|A|Sada SDK musí projít [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)]-konkrétní koncepty balení a F5 pracovat správně s sady SDK k dispozici v [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)].|A|Obsah NuGet stane součástí projektu. Je potřeba žádné zvláštní ohledy F5.|
|Tento mechanismus nasadí soubory – referenční dokumentace (například nasadit test framework, při kterém se má spouštět testy [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace).|A|Pokud je vyřadit soubory *\redist* složky, soubory se automaticky nasadí.|A||
|Tento mechanismus v prostředí Visual Studio IDE automaticky přidá platformy sady SDK.|A|Pokud je vyřadit [!INCLUDE[win8](../debugger/includes/win8_md.md)] SDK nebo sady Windows Phone SDK v konkrétní umístění s konkrétní rozložení, sady SDK automaticky integruje se všemi funkcemi sady Visual Studio.|N||
|Tento mechanismus podporuje počítače s čistou vývojáře. (To znamená, není třeba žádná instalace, a bude fungovat jednoduché načtení ze správy zdrojového kódu.)|N|Protože odkazujete sady SDK, musíte zkontrolovat, v řešení a sady SDK samostatně. Můžete zkontrolovat v sadě SDK ze dvou bez registru výchozí umístění, ze kterých MSBuild opakuje sady SDK (podrobnosti najdete v tématu [vytváření Software Development Kit](../extensibility/creating-a-software-development-kit.md)). Jako alternativu Pokud do vlastního umístění se skládá ze sady SDK můžete určit následující kód v souboru projektu:<br /><br /> `<PropertyGroup>    <SDKReferenceDirectoryRoot>C:\MySDKs</SDKReferenceDirectoryRoot>   </PropertyGroup>`<br /><br /> Zkontrolujte sady SDK do tohoto umístění.|A|Můžete zkontrolovat na řešení a Visual Studio okamžitě rozpozná a funguje na soubory.|
|Toho se můžete zapojit velké existující komunity autorů balíčku.|Není k dispozici|Komunita je nová.|A||
|Můžete připojit velké existující komunitou příjemců balíčku.|Není k dispozici|Komunita je nová.|A||
|Můžete připojit ekosystém partnerů (Vlastní galerie, úložiště a tak dále).|Není k dispozici|K dispozici úložiště zahrnují Visual Studio Marketplace, Microsoft Download Center a [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)].|A||
|Tento mechanismus se integruje s servery průběžnou integraci sestavení pro vytvoření balíčku a využití.|A|Sada SDK musí předat umístění vráceno se změnami (vlastnost SDKReferenceDirectoryRoot) na příkazovém řádku MSBuild.|A||
|Tento mechanismus podporuje obě verze stabilní a předběžné verze balíčků.|A|SDK podporuje přidávání odkazů na více verzí.|A||
|Tento mechanismus podporuje automatickou aktualizaci pro nainstalované balíčky.|A|Pokud je dodávána jako součást sady Visual Studio automatických aktualizací nebo VSIX, sada SDK poskytuje automatické oznámení.|A||
|Tento mechanismus obsahuje samostatný *.exe* soubor pro vytváření a použití balíčků.|A|Sada SDK obsahuje *MSBuild.exe*.|A||
|Balíčky můžete změnami do správy verzí.|A|Nelze změnami nic mimo uzlu dokumentů, což znamená, že rozšíření sady SDK nemusí být vráceny se změnami. Velikost rozšíření sady SDK může být velký.|A||
|Rozhraní PowerShell můžete vytvářet a využívat balíčky.|Y (spotřeba), N (vytvoření)|Žádné nástrojů pro vytvoření sady SDK. Spotřeba provádí MSBuild v příkazovém řádku.|A||
|Můžete vytvořit balíček Symbol pro ladění podpory.|A|Pokud je vyřadit *PDB* soubory v sadě SDK, soubory získat zachyceny automaticky.|A||
|Tento mechanismus podporuje balíček správce automatické aktualizace.|Není k dispozici|Pomocí nástroje MSBuild získá revize sady SDK.|A||
|Tento mechanismus podporuje lightweight manifestu formátu.|A|*SDKManifest.xml* podporuje mnoho atributů, ale pouze malou je obvykle potřeba.|A||
|Tento mechanismus je k dispozici pro všechny edice sady Visual Studio.|A|SDK podporuje všechny edice sady Visual Studio.|A|NuGet podporuje všechny verze sady Visual Studio.|
|Tento mechanismus je k dispozici pro všechny typy projektů.|N|SDK podporuje [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace počínaje [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|N|Můžete zkontrolovat seznam povolených projekty.|

## <a name="see-also"></a>Viz také

[Správa odkazů v projektu](../ide/managing-references-in-a-project.md)
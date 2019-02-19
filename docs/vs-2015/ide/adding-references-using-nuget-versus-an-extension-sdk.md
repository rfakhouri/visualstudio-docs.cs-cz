---
title: Přidání odkazů pomocí nástroje NuGet a sady Extension SDK | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.toolsoptionspages.nuget_package_manager.general
- vs.toolsoptionspages.nuget_package_manager.package_sources
ms.assetid: 2175581e-83cb-444c-bb52-cc1fca8ea196
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 29590b96a8d8d2ad8fbddaf0d97b9ed55e6aadf2
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54763595"
---
# <a name="adding-references-using-nuget-versus-an-extension-sdk"></a>Přidání odkazů pomocí nástroje NuGet a sady Extension SDK
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Balíček pro použití v rámci projektů sady Visual Studio můžete zadat prostřednictvím rozšíření NuGet sady Visual Studio, nebo (SDK) software development kit. Zadáním popisu vašeho nového podobnosti a rozdíly mezi dva mechanismy, v tomto tématu vám můžou pomoct vybrat ten nejlepší pro vaše úlohy.  
  
-   NuGet je open source systém správy balíčků, který slouží ke zjednodušení procesu začlenění knihoven do řešení projekt. Další informace najdete v tématu [NuGet přehled](http://go.microsoft.com/fwlink/?LinkId=254877).  
  
-   Sada SDK je kolekce souborů, které Visual Studio považuje za položku jeden odkaz. **Správce odkazů** dialogové okno obsahuje všechny sady SDK, které se vztahují k projektu, která je otevřená, při zobrazení tohoto pole dialogového okna. Při přidání sady SDK do projektu, můžete celý obsah této sady SDK přistupovat prostřednictvím technologie IntelliSense, **nástrojů**, návrháři, **prohlížeče objektů**, MSBuild, nasazení, ladění a balení. Další informace o sadách SDK najdete v tématu [vytváření Software Development Kit](../extensibility/creating-a-software-development-kit.md).  
  
## <a name="which-mechanism-should-i-use"></a>Které mechanismus mám použít?  
 Následující tabulka vám pomůže porovnat odkazující funkcí sady SDK odkazující funkcí NuGet.  
  
|Funkce|Podpora v sadě SDK|Poznámky k sady SDK|Podpora NuGet|Poznámky k NuGet|  
|-------------|-----------------|---------------|-------------------|-----------------|  
|Mechanismu, který odkazuje na jednu entitu a pak všechny soubory a funkce jsou k dispozici.|Ano|Přidat sadu SDK s použitím **správce odkazů** dialogové okno a všechny soubory a funkce jsou k dispozici během pracovního postupu vývoje.|Ano||  
|Nástroj MSBuild automaticky využívá sestavení a souborů metadat (.winmd) pro Windows.|Ano|Odkazy v sadě SDK automaticky jsou předány kompilátoru.|Ano||  
|Nástroj MSBuild automaticky využívá soubory hlaviček nebo lib.|Ano|*SDKName*soubor PROPS nastavení adresáře Visual C++ a tak dále, pro automatické použití souboru .h nebo .lib instruuje Visual Studio.|N||  
|Nástroj MSBuild automaticky zpracovává soubory JS a CSS.|Ano|V **Průzkumníka řešení**, můžete rozbalit uzel odkazu JavaScript SDK na ukazují jednotlivých .js nebo .css soubory a pak vygenerovat `<source include/>` značky přetažením tyto soubory do jejich zdrojové soubory. Sada SDK podporuje F5 a automatické balíček instalačního programu.|Ano||  
|Nástroj MSBuild automaticky přidá ovládacího prvku **nástrojů**.|Ano|**Nástrojů** může spotřebovávat sady SDK a zobrazit ovládací prvky na kartách, které zadáte.|N||  
|Mechanismu, který podporuje instalační program sady Visual Studio pro rozšíření (VSIX).|Ano|VSIX má zvláštní manifestu a logiku a vytváření balíčků sady SDK|Ano|VSIX může být vložen do jiné instalační program.|  
|**Prohlížeče objektů** vytvoří výčet odkazy.|Ano|**Prohlížeče objektů** automaticky načte seznam odkazů v sadách SDK a zobrazí je.|N||  
|Soubory a odkazy automaticky přidají do **správce odkazů** dialogové okno (odkazy na nápovědu a podobně automaticky naplnit)|Ano|**Správce odkazů** sad SDK, dialogové okno automaticky zobrazí spolu s odkazy na nápovědu a seznam závislostí sady SDK.|N|NuGet poskytuje vlastní **spravovat balíčky NuGet** dialogové okno.|  
|Mechanismu, který podporuje několik architektur.|Ano|Sady SDK se dají dodávat více konfigurací. Nástroj MSBuild používá příslušné soubory pro každou konfiguraci projektu.|N||  
|Mechanismu, který podporuje víc konfigurací.|Ano|Sady SDK se dají dodávat více konfigurací. V závislosti na architektuře projektu MSBuild používá příslušné soubory pro každou architekturu projektu.|N||  
|Tento mechanismus lze vybrat "není kopie."|Ano|V závislosti na tom, jestli se zahodí soubory ve složce \redist nebo \designtime můžete určit, které soubory chcete zkopírovat do balíčku spotřebitelskou aplikací.|N|Deklarujete souborů, které chcete kopírovat v manifestu balíčku.|  
|Zobrazí se obsah ve lokalizované soubory.|Ano|Lokalizované dokumenty XML v sadách SDK budou zahrnuty automaticky návrhové prostředí lépe.|N||  
|Nástroj MSBuild podporuje současně spotřebovává více verzí sady SDK.|Ano|Sada SDK podporuje současně spotřebovává více verzí.|N|To není odkazuje. Nemůže mít více než jedna verze NuGet soubory v projektu v čase.|  
|Mechanismu, který podporuje zadání příslušné cílové architektury, verze sady Visual Studio a typy projektů.|Ano|**Správce odkazů** dialogové okno a **nástrojů** zobrazit pouze se sadami SDK služby, které se vztahují k projektu, aby uživatelé mohli snadněji vybrat odpovídající sady SDK.|Y (částečná podpora)|Oddíl je cílovou architekturu. Neexistuje žádné filtrování na uživatelské rozhraní. Během instalace může vrátit chybu.|  
|Mechanismu, který podporuje zadání informací o registraci pro nativní soubory Winmd.|Ano|Korelace mezi soubor winmd a DLL můžete zadat v SDKManifest.xml.|N||  
|Tento mechanismus podporuje určení závislostí na jiných sad SDK.|Ano|Sada SDK pouze upozorní uživatele. Uživatel musí stále je nainstalovat a ručně na ně odkazují.|Ano|NuGet si vyžádá je automaticky. uživateli nezobrazí upozornění.|  
|Mechanismu, který se integruje s [!INCLUDE[win8_appstore_long](../includes/win8-appstore-long-md.md)] konceptů, jako jsou manifest aplikace a ID rámce.|Ano|Sada SDK musí projít koncepty, které jsou specifické pro [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)] , balení a F5 pracovat správně s sad SDK, které jsou k dispozici v[!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)].|N||  
|Mechanismu, který se integruje s ladění kanálu pro aplikace [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] aplikace.|Ano|Sada SDK musí projít [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)]-konkrétní informace, balení a F5 pracovat správně se sadami SDK dostupnými v [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)].|Ano|NuGet obsahu se stane součástí projektu. Je potřeba žádná zvláštní pozornost F5.|  
|Mechanismu, který se integruje s manifesty aplikací.|Ano|Sada SDK musí projít [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)]-konkrétní informace, balení a F5 pracovat správně se sadami SDK dostupnými v [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)].|Ano|NuGet obsahu se stane součástí projektu. Je potřeba žádná zvláštní pozornost F5.|  
|Mechanismus nasadí soubory – referenční dokumentace (například nasadit testovací rozhraní, na kterém budete spouštět testy z [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] aplikace).|Ano|Pokud odstraníte soubory ve složce \redist, soubory se automaticky nasadí.|Ano||  
|Mechanismus automaticky přidá platformy sady SDK v sadě Visual Studio IDE.|Ano|Pokud přetáhnete [!INCLUDE[win8](../includes/win8-md.md)] SDK nebo Windows Phone SDK v konkrétním umístění s specifické rozložení, sada SDK automaticky integrován se všemi funkcemi sady Visual Studio.|N||  
|Mechanismu, který podporuje počítače čisté pro vývojáře. (To znamená, bez instalace je povinný a jednoduché načtení ze správy zdrojového kódu bude fungovat.)|N|Vzhledem k tomu, že budete odkazovat na sadu SDK, musíte zkontrolovat, v řešení a sady SDK odděleně. Můžete zkontrolovat v sadě SDK ze dvou bez registru výchozí umístění, ze kterých MSBuild iterace, sady SDK (podrobnosti najdete v tématu [vytváření Software Development Kit](../extensibility/creating-a-software-development-kit.md)). Případně pokud vlastní umístění se skládá ze sady SDK, můžete zadat následující kód v souboru projektu:<br /><br /> `<PropertyGroup>    <SDKReferenceDirectoryRoot>C:\MySDKs</SDKReferenceDirectoryRoot>   </PropertyGroup>`<br /><br /> Potom zkontrolujte sady SDK do tohoto umístění.|Ano|Si můžete prohlédnout řešení a sady Visual Studio okamžitě rozpozná a funguje na souborech.|  
|Můžete připojit velký existující komunity autorů balíčků.|Není k dispozici|Novinky v komunitě.|Ano||  
|Můžete připojit rozsáhlou existující komunitou příjemců balíčku.|Není k dispozici|Novinky v komunitě.|Ano||  
|Můžete připojit ekosystémem partnerů (Vlastní galerie, úložiště a tak dále).|Není k dispozici|K dispozici úložiště zahrnují Galerie sady Visual Studio, Microsoft Download Center a [!INCLUDE[win8_appstore_long](../includes/win8-appstore-long-md.md)].|Ano||  
|Mechanismu, který se integruje s servery sestavení kontinuální integrace pro vytvoření balíčku a spotřebu.|Ano|Sady SDK musí předat umístění vrácené se změnami (SDKReferenceDirectoryRoot vlastností) na příkazovém řádku MSBuild.|Ano||  
|Mechanismu, který podporuje obě verze stabilní a předběžné verze balíčků.|Ano|Sada SDK podporuje přidávání odkazů na více verzí.|Ano||  
|Mechanismu, který podporuje automatickou aktualizaci pro nainstalované balíčky.|Ano|Pokud dodán jako součást automatické aktualizace sady Visual Studio nebo VSIX, sada SDK poskytuje automatické oznamování.|Ano||  
|Mechanismu, který obsahuje soubor samostatné .exe pro vytváření a využívání balíčků.|Ano|Tato sada SDK obsahuje MSBuild.exe.|Ano||  
|Balíčky může být zařazeno do správy verzí.|Ano|Nelze je vrátit se změnami něco mimo uzlu dokumenty, což znamená, že rozšíření sady SDK nemusí být vráceny se změnami. Sady SDK rozšíření může být velký.|Ano||  
|Rozhraní prostředí PowerShell můžete použít k vytváření a využívání balíčků.|Y (spotřeba), N (vytvoření)|Žádné nástroje pro vytvoření sady SDK. Spotřeba spouští MSBuild na příkazovém řádku.|Ano||  
|Balíček symbolů můžete použít pro podporu ladění.|Ano|Pokud odstraníte soubory typu .pdb v sadě SDK, soubory získat nenačítají automaticky.|Ano||  
|Mechanismu, který podporuje Správce balíčků automatické aktualizace.|Není k dispozici|Sada SDK získá revize pomocí nástroje MSBuild.|Ano||  
|Mechanismu, který podporuje jednoduchý formát manifestu.|Ano|SDKManifest.xml podporuje mnoho atributů, ale malou je obvykle nezbytná.|Ano||  
|Tento mechanismus je k dispozici pro všechny edice sady Visual Studio.|Ano|Sada SDK podporuje všechny edice sady Visual Studio z Visual Studio Express prostřednictvím [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)].|Ano|NuGet podporuje všechny edice sady Visual Studio Express až prostřednictvím [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)].|  
|Tento mechanismus je k dispozici pro všechny typy projektů.|N|Sada SDK podporuje [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] aplikace od [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)].|N|Můžete zkontrolovat seznam povolených projektů.|  
  
## <a name="see-also"></a>Viz také  
 [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)

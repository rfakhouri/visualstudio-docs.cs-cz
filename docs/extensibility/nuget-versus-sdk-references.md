---
title: Přidání odkazů pomocí nástroje NuGet a sady Extension SDK
ms.date: 08/02/2019
ms.topic: conceptual
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 372e82f9bb032ac5a81362017d2062ecf0d44e3f
ms.sourcegitcommit: a124076dfd6b4e5aecda4d01984fee7b0c034745
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2019
ms.locfileid: "68795082"
---
# <a name="nuget-versus-sdk-as-a-project-reference"></a>NuGet oproti sadě SDK jako odkaz na projekt

Tento článek je navržený tak, aby pomáhal vývojářům zvolit, jestli chcete zabalit software jako balíček NuGet nebo jako sadu SDK (Software Development Kit). Konkrétně popisuje rozdíly mezi těmito dvěma při jejich odkazování v projektu sady Visual Studio.

- [NuGet](/nuget) je open source systém pro správu balíčků, který zjednodušuje proces začleňování knihoven do projektu. Pro .NET (včetně .NET Core) je NuGet Microsoftem podporovaný mechanizmus pro sdílení kódu. NuGet definuje, jak se vytvářejí, hostují a spotřebovávají balíčky pro .NET, a poskytuje nástroje pro každou z těchto rolí. V aplikaci Visual Studio přidáte balíčky NuGet do projektu pomocí uživatelského rozhraní [Správce balíčků](/nuget/consume-packages/install-use-packages-visual-studio) .

- [Sada SDK](../extensibility/creating-a-software-development-kit.md) je kolekce souborů, které Visual Studio považuje za položku s jedinou referencí. Dialogové okno Správce odkazů v aplikaci Visual Studio obsahuje seznam všech sad SDK, které jsou relevantní pro aktuální projekt, pokud zvolíte možnost **Přidat odkaz**. Když přidáte sadu SDK do projektu, můžete ke všem obsahem této sady SDK přistupovat prostřednictvím technologie IntelliSense, okna nástrojů, návrháře, Prohlížeč objektů, MSBuild, nasazení, ladění a balení.

## <a name="which-mechanism-should-i-use"></a>Který mechanismus mám použít?

Následující tabulka vám pomůže porovnat referenční funkce sady SDK s referenčními funkcemi NuGet.

| Funkce | Podpora sady SDK | Poznámky k sadě SDK | Podpora NuGet | Poznámky k NuGetu |
| - | - | - |---------------| - |
| Mechanismus odkazuje na jednu entitu a všechny soubory a funkce jsou k dispozici. | Ano | Sadu SDK můžete přidat pomocí dialogového okna **Správce odkazů** a všechny soubory a funkce jsou k dispozici během vývojového pracovního postupu. | Ano | |
| Nástroj MSBuild automaticky spotřebovává sestavení a soubory metadat Windows ( *. winmd*). | Ano | Odkazy v sadě SDK jsou automaticky předány kompilátoru. | Ano | |
| Nástroj MSBuild automaticky spotřebovává soubory. h nebo. lib. | Ano | Soubor *SDKName. props* oznamuje sadě Visual Studio, jak nastavit adresář vizuálu C++ a tak dále pro automatickou spotřebu souborů *. h* nebo *. lib* . | N | |
| Nástroj MSBuild automaticky spotřebovává soubory *. js* nebo *. CSS* . | Ano | V **Průzkumník řešení**můžete rozbalit referenční uzel sady JavaScript SDK pro zobrazení individuálních souborů *. js* nebo *.* potom je možné vygenerovat `<source include/>` značky přetažením těchto souborů do zdrojových souborů. Sada SDK podporuje F5 a automatickou instalaci balíčků. | Ano | |
| Nástroj MSBuild automaticky přidá ovládací prvek do **panelu nástrojů**. | Ano | **Sada nástrojů** může využívat sady SDK a zobrazovat ovládací prvky na kartách, které zadáte. | N | |
| Mechanismus podporuje Instalační program pro Visual Studio pro rozšíření (VSIX). | Ano | VSIX má speciální manifest a logiku pro vytváření balíčků sady SDK. | Ano | VSIX lze vložit do jiného instalačního programu. |
| **Prohlížeč objektů** výčtu odkazů. | Ano | **Prohlížeč objektů** automaticky získá seznam odkazů v sadách SDK a vytvoří jejich výčet. | N | |
| Soubory a odkazy se automaticky přidají do dialogového okna **Správce odkazů** (odkazy Nápověda a automaticky naplní se tak dál). | Ano | V dialogovém okně **Správce odkazů** se automaticky vyčíslují sady SDK společně s odkazy na Help a seznamem závislostí SDK. | N | NuGet poskytuje vlastní dialogové okno **Spravovat balíčky NuGet** . |
| Mechanismus podporuje více architektur. | Ano | Sady SDK mohou dodávat více konfigurací. Nástroj MSBuild využívá příslušné soubory pro každou konfiguraci projektu. | N | |
| Mechanismus podporuje více konfigurací. | Ano | Sady SDK mohou dodávat více konfigurací. V závislosti na architektuře projektu nástroj MSBuild spotřebovává příslušné soubory pro každou architekturu projektu. | N | |
| Mechanismus může určovat "ne pro kopírování". | Ano | V závislosti na tom, jestli jsou soubory vyřazené ve složce *\redist* nebo *\DesignTime* , můžete určit, které soubory se mají zkopírovat do balíčku náročné aplikace. | N | Deklarujete, které soubory se mají zkopírovat v manifestu balíčku. |
| Obsah se zobrazí v lokalizovaných souborech. | Ano | Lokalizované dokumenty XML v sadách SDK jsou automaticky zahrnuty pro lepší prostředí pro dobu návrhu. | N | |
| Nástroj MSBuild podporuje současně více verzí sady SDK. | Ano | Sada SDK podporuje současné využívání více verzí současně. | N | Neodkazuje se na. V projektu nemůžete mít více než jednu verzi souborů NuGet. |
| Mechanismus podporuje určení příslušných cílových rozhraní, verzí sady Visual Studio a typů projektů. | Ano | Dialogové okno **Správce odkazů** a **panel nástrojů** zobrazují pouze sady SDK, které se vztahují k projektu, takže uživatelé mohou snadněji zvolit příslušné sady SDK. | Y (částečně) | Pivot je cílová architektura. Neexistuje žádné filtrování na uživatelském rozhraní. V době instalace může vrátit chybu. |
| Mechanismus podporuje určení registračních informací pro nativní soubory WinMD. | Ano | Můžete zadat korelaci mezi souborem. winmd a souborem. dll v souboru *SDKManifest. XML*. | N | |
| Mechanismus podporuje určení závislostí na jiných sadách SDK. | Ano | Sada SDK upozorní uživatele pouze na to, uživatel je musí pořád nainstalovat a odkazovat na ně ručně. | Ano | NuGet je automaticky vyžádá; uživatel není upozorněn. |
| Mechanismus se integruje s [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)] koncepty, jako je manifest aplikace a ID rozhraní. | Ano | Sada SDK musí předat koncepty specifické pro [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)] , aby balíčky a F5 správně fungovaly se sadami SDK, které jsou k dispozici[!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)]v nástroji. | N | |
| Mechanismus se integruje s kanálem ladění aplikace pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace. | Ano | Sada SDK musí předávat [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)]konkrétní koncepce, aby balíčky a F5 správně pracovaly se sadami SDK dostupnými [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)]v nástroji. | Ano | Obsah NuGet se stal součástí projektu. Nevyžaduje se žádný zvláštní aspekt F5. |
| Mechanismus se integruje s manifesty aplikací. | Ano | Sada SDK musí předávat [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)]konkrétní koncepce, aby balíčky a F5 správně pracovaly se sadami SDK dostupnými [!INCLUDE[win8_appstore_short](../ide/includes/win8_appstore_short_md.md)]v nástroji. | Ano | Obsah NuGet se stal součástí projektu. Nevyžaduje se žádný zvláštní aspekt F5. |
| Mechanismus nasadí nereferenční soubory (například nasazení testovacího rozhraní, na kterém se mají spouštět testy [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikací). | Ano | Pokud soubory odstraníte ve složce *\redist* , soubory se automaticky nasadí. | Ano | |
| Mechanismus automaticky přidá sady SDK platformy v integrovaném vývojovém prostředí sady Visual Studio. | Ano | Pokud [!INCLUDE[win8](../debugger/includes/win8_md.md)] sadu SDK nebo sadu Windows Phone SDK z konkrétního umístění vyřadíte pomocí konkrétního rozložení, sada SDK se automaticky integruje se všemi funkcemi sady Visual Studio. | N | |
| Mechanismus podporuje čistý vývojový počítač. (To znamená, že není nutná žádná instalace a jednoduché načtení ze správy zdrojového kódu bude fungovat.) | N | Vzhledem k tomu, že odkazujete na sadu SDK, je nutné vrátit se změnami řešení a sadu SDK samostatně. Sadu SDK můžete vrátit se změnami ze dvou výchozích umístění, ze kterých nástroj MSBuild prochází sady SDK (podrobnosti najdete v tématu [Vytvoření sady Software Development Kit](../extensibility/creating-a-software-development-kit.md)). Alternativně, pokud se vlastní umístění skládá ze sad SDK, můžete zadat následující kód v souboru projektu:<br /><br />`<PropertyGroup>`<br />&nbsp;&nbsp;`<SDKReferenceDirectoryRoot>`<br />&nbsp;&nbsp;`C:\MySDKs`<br />&nbsp;&nbsp;`</SDKReferenceDirectoryRoot>`<br />`</PropertyGroup>`<br /><br /> Pak zkontrolujte sady SDK do tohoto umístění. | Ano | Můžete se podívat na řešení a Visual Studio okamžitě rozpoznává a funguje na souborech. |
| Můžete se připojit k velkému stávajícímu komunitnímu tvůrci balíčků. | Není k dispozici | Komunita je nová. | Ano | |
| Můžete se připojit k velkému stávajícímu komunitě uživatelů balíčku. | Není k dispozici | Komunita je nová. | Ano | |
| Můžete se připojit k ekosystému partnerů (vlastní galerie, úložiště a tak dále). | Není k dispozici | Mezi dostupná úložiště patří Visual Studio Marketplace, Microsoft Download Center a [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]. | Ano | |
| Mechanismus se integruje se servery sestavení průběžné integrace pro vytváření a spotřebu balíčku. | Ano | Sada SDK musí předat umístění vráceného se změnami (vlastnost SDKReferenceDirectoryRoot) na příkazovém řádku do nástroje MSBuild. | Ano | |
| Mechanismus podporuje jak stabilní, tak i předběžné verze balíčků. | Ano | Sada SDK podporuje přidávání odkazů na více verzí. | Ano | |
| Mechanismus podporuje automatické aktualizace nainstalovaných balíčků. | Ano | Pokud je dodán jako VSIX nebo součást automatických aktualizací sady Visual Studio, poskytuje sada SDK automatická oznámení. | Ano | |
| Mechanismus obsahuje samostatný soubor *. exe* pro vytváření a využívání balíčků. | Ano | Sada SDK obsahuje *MSBuild. exe*. | Ano | |
| Balíčky lze vrátit se změnami do řízení verze. | Ano | Nemůžete vrátit cokoli mimo uzel dokumenty, což znamená, že sady SDK rozšíření nemusí být vráceny se změnami. Velikost sady SDK rozšíření může být velká. | Ano | |
| K vytváření a využívání balíčků můžete použít rozhraní PowerShellu. | Y (spotřeba), N (vytváření) | Žádné nástroje pro vytvoření sady SDK. Spotřeba spouští nástroj MSBuild na příkazovém řádku. | Ano | |
| Pro podporu ladění můžete použít balíček symbolů. | Ano | Při vyřazení souborů *. pdb* v sadě SDK se soubory automaticky vybírají. | Ano | |
| Mechanismus podporuje automatické aktualizace správce balíčků. | Není k dispozici | Sada SDK se bude revidována pomocí nástroje MSBuild. | Ano | |
| Mechanismus podporuje odlehčený formát manifestu. | Ano | *SDKManifest. XML* podporuje mnoho atributů, ale je obvykle zapotřebí malá podmnožina. | Ano | |
| Mechanismus je k dispozici pro všechny edice sady Visual Studio. | Ano | Sada SDK podporuje všechny edice sady Visual Studio. | Ano | NuGet podporuje všechny edice sady Visual Studio. |

## <a name="see-also"></a>Viz také:

- [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)
- [Správa odkazů v projektu (Visual Studio pro Mac)](/visualstudio/mac/managing-references-in-a-project)
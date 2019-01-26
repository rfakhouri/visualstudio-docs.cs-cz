---
title: Přepínače příkazového řádku nástroje DEVENV pro vývoj rozšíření VSPackage | Dokumentace Microsoftu
ms.date: 12/10/2018
ms.topic: conceptual
helpviewer_keywords:
- /Setup command line switch
- /ResetSkipPkgs command line switch
- /RootSuffix command line switch
- /SafeMode command line switch
- /Splash command line switch
- command-line switches
- registry, Visual Studio SDK
- command line, switches
- Visual Studio SDK, command-line switches
ms.assetid: d65d2c04-dd84-42b0-b956-555b11f5a645
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 89114689f933f3b09aac1d7ffcec109e81f631ad
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54970549"
---
# <a name="devenv-command-line-switches-for-vspackage-development"></a>Přepínače příkazového řádku nástroje DEVENV pro vývoj rozšíření VSPackage

Visual Studio umožňuje vývojářům automatizovat úlohy z příkazového řádku při provádění `devenv.exe`, soubor, který se spustí rozhraní IDE sady Visual Studio.  

 Mezi úlohy patří:  

- Nasazení aplikací v předem navrženými konfigurace z mimo rozhraní IDE.  

- Vytváření projektů pomocí přednastavených automaticky nastavení sestavení nebo konfiguraci ladění.  

- Načítání integrovaného vývojového prostředí v konkrétní konfigurace, z mimo rozhraní IDE. Můžete také přizpůsobit IDE po spuštění.  

## <a name="guidelines-for-switches"></a>Pokyny pro přepínače

Dokumentace k sadě Visual Studio popisuje uživatelské úrovni `devenv` přepínače příkazového řádku. Další informace najdete v tématu [přepínače příkazového řádku nástroje Devenv](../ide/reference/devenv-command-line-switches.md). `devenv` Nástroj také podporuje další přepínače příkazového řádku, které jsou užitečné se VSPackage vývoje, nasazení a ladění.  

| Přepínač příkazového řádku | Popis |
|---------------------| - |
| `/ResetSkipPkgs` | Vymaže všechny možnosti načítání přeskočit, které jste přidali uživatele, kteří mají předejít problematické rozšíření VSPackages a pak spustí Visual Studio. Přítomnost značky SkipLoading zakáže načítání VSPackage. Vymazává se značka znovu povolí načítání sady VSPackage.<br /><br /> Tento přepínač nepřijímá žádné argumenty. |
| `/RootSuffix` | Spustí Visual Studio pomocí alternativního umístění. Zástupce vytvořil instalační program sady Visual Studio SDK je spusťte následující příkaz:<br /><br /> `devenv /RootSuffix exp`<br /><br /> V takovém případě `exp` identifikuje umístění s konkrétní příponou (například `10.0Exp` místo `10.0`). Experimentální instanci umožňuje ladit VSPackage odděleně od instance sady Visual Studio, který používáte k psaní kódu.<br /><br /> Tento přepínač můžete využít libovolný řetězec, který identifikuje, kterou jste vytvořili pomocí VSRegEx.exe umístění. Další informace najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md). |
| `/SafeMode` | Spustí sadu Visual Studio v nouzovém režimu, načítání výchozí integrovaného vývojového prostředí a služeb. `/SafeMode` Přepínač brání načtení při spuštění sady Visual Studio, zajišťují stabilní provádění všech rozšíření VSPackages třetích stran.<br /><br /> Tento přepínač nepřijímá žádné argumenty. |
| `/Setup` | Vynutí Visual Studio ke sloučení resource metadata, která popisuje nabídky, panely nástrojů a příkaz skupiny ze všech dostupných rozšíření VSPackages. Tento příkaz může běžet jenom jako správce. <br /><br /> Tento přepínač nepřijímá žádné argumenty. `devenv /Setup` Příkaz je obvykle poskytnuta jako poslední krok z procesu instalace. Použití `/Setup` přepínač nelze spustit prostředí IDE.|
| `/Splash` | Obrazovky jako obvykle, a poté zobrazí zprávu pole před zobrazením hlavní integrovaného vývojového prostředí se zobrazí úvodní sady Visual Studio. Okno se zprávou vám umožňuje zkoumat na úvodní obrazovce (například hledat ikona produktu VSPackage).<br /><br /> Tento přepínač nepřijímá žádné argumenty. |

## <a name="see-also"></a>Viz také:

- [Přidání přepínačů příkazového řádku](../extensibility/adding-command-line-switches.md)
- [Přepínače příkazového řádku nástroje devenv](../ide/reference/devenv-command-line-switches.md)
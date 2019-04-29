---
title: Vyhledání sady Visual Studio | Dokumentace Microsoftu
ms.date: 08/21/2017
ms.topic: conceptual
helpviewer_keywords:
- deployment, VSIX
ms.assetid: 680c3b25-7901-4768-8363-6d1fcd1ea636
ms.author: heaths
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c13146d0d48dc176417040bcb756bf8069ad3c3e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62907299"
---
# <a name="locate-visual-studio"></a>Vyhledejte Visual Studio

Od verze Visual Studio 2017, můžete nainstalovat více instancí stejné verze nebo dokonce edition. To je užitečné, pokud chcete zobrazit náhled nové funkce ve primárního vývojového počítače a zajistit přitom ochranu předchozí instalace. Z důvodů těchto změn neexistuje jedno prostředí proměnné nebo registru hodnota, která vám pomůže najít instanci. Místo toho můžete použít [rozhraní API modelu COM dotazu](https://msdn.microsoft.com/library/microsoft.visualstudio.setup.configuration.aspx) najít instancí na základě kritérií, které jsou relevantní pro rozšíření.

Toto je rychlý a jen pro čtení rozhraní API s balíčky NuGet, které jsou k dispozici pro nativní a spravovaný kód.

| Kód | Balíček |
| ---- | --- |
| Nativní | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Native |
| Spravovaní | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Interop |

Můžete najít jednu instanci cestu nebo aktuální proces, nebo vytvořit výčet všech instancí. Zobrazit [našich ukázek](https://github.com/Microsoft/vs-setup-samples) kompletní příklady toho, jak najít sady Visual Studio.

## <a name="tools"></a>Nástroje

Visual Studio a dalších nástrojů najdete v prostředí sestavení, skriptů prostředí PowerShell, instalační programy a další scénáře, existuje mnoho open source nástrojů můžete přímo použít nebo si znovu distribuovat spolu s vlastní skripty.

| Project | Popis |
| ------- | ----------- |
| [vswhere](https://github.com/Microsoft/vswhere) | Jedním souborem nativní spustitelný soubor k vyhledání instance splňující kritéria, například vydání nebo předběžné verze, jaké produkt je nainstalovaný a úlohy, které jsou nainstalovány. Podporuje také vyhledání sady Visual Studio 2010 a novější, ale méně informací je vrácena, který pro Visual Studio 2017 a novější. Zobrazit [wiki](https://github.com/Microsoft/vswhere/wiki) příklady. |
| [Rutiny VSSetup](https://github.com/Microsoft/vssetup.powershell) | Podporované rutin prostředí PowerShell 2.0 a novějších verzí, které vracejí široké škály informací jako objekty můžete použít k vyhledání instance na základě kritérií stejné jako _vswhere_ a zjišťování ještě více vlastností o instancích. Zobrazit [wiki](https://github.com/Microsoft/vssetup.powershell/wiki) příklady. |
| [VSIXBootstrapper](https://github.com/Microsoft/vsixbootstrapper) | Automaticky vyhledá _VSIXInstaller_ a předává prostřednictvím příkazového řádku pro instalaci **VSIX* souboru. Tato funkce může být užitečné pro instalační programy, které nemají přímou podporu pro dotaz rozhraní API. Zobrazit [wiki](https://github.com/Microsoft/vsixbootstrapper/wiki) příklady. |

## <a name="see-also"></a>Viz také:

* [Změny v instalaci sady Visual Studio 2017](https://devblogs.microsoft.com/setup/changes-to-visual-studio-15-setup/)

---
title: Vyhledání sady Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 08/21/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- deployment, VSIX
ms.assetid: 680c3b25-7901-4768-8363-6d1fcd1ea636
ms.author: heaths
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ed6125c69b9068ebfb3d776ccbefaf88043f83a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138610"
---
# <a name="locating-visual-studio"></a>Vyhledání sady Visual Studio

Od verze Visual Studio 2017, můžete nainstalovat víc instancí stejnou verzi nebo edici i. To je užitečné, pokud chcete zobrazit náhled nové funkce na primární vývojovém počítači a přitom zachovat předchozí instalace. Tyto změny jednoho prostředí proměnnou nebo registru hodnota neexistuje, které můžete použít k vyhledání instance. Místo toho můžete použít [rozhraní API modelu COM dotazu](https://msdn.microsoft.com/library/microsoft.visualstudio.setup.configuration.aspx) najít instancí na základě kritérií, které jsou relevantní pro rozšíření.

Toto je rychlé, jen pro čtení rozhraní API pomocí balíčků NuGet, které jsou k dispozici pro nativního a spravovaného kódu.

| Kód | Balíček |
| ---- | --- |
| Nativní | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Native |
| Spravované | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Interop |

Můžete najít jedna instance pro danou cestu nebo aktuální proces, nebo vytvořit výčet všech instancí. V tématu [naše ukázky](https://github.com/Microsoft/vs-setup-samples) pro dokončení příklady, jak najít sady Visual Studio.

## <a name="tools"></a>Nástroje

Visual Studio a dalších nástrojů najdete v prostředí sestavení, skripty prostředí PowerShell, instalační programy a další scénáře, máme několik nástrojů s otevřeným zdrojem můžete použít přímo, nebo znovu distribuovat spolu s vlastní skripty.

| Projekt | Popis |
| ------- | ----------- |
| [vswhere](https://github.com/Microsoft/vswhere) | Nativní jedním souborem spustitelný soubor vyhledat instance splnění kritérií, například verze nebo předběžné verze, jaké produkt je nainstalován a úlohy, které jsou nainstalovány. Podporuje také hledání Visual Studio 2010 a novější, i když menší se vrátí informace, pro Visual Studio 2017 a novějších. Najdete v článku [wiki](https://github.com/Microsoft/vswhere/wiki) příklady. |
| [Rutiny VSSetup](https://github.com/Microsoft/vssetup.powershell) | Podporované rutiny prostředí PowerShell 2.0 a novější, které vrací bohaté informace jako objekty, můžete použít k vyhledání instancí na základě kritérií stejné jako _vswhere_ a zjistit, o instancích i další vlastnosti. Najdete v článku [wiki](https://github.com/Microsoft/vssetup.powershell/wiki) příklady. |
| [VSIXBootstrapper](https://github.com/Microsoft/vsixbootstrapper) | Automaticky vyhledá _VSIXInstaller_ a předá prostřednictvím příkazového řádku pro instalaci _*.vsix_ souboru. To může být užitečné v instalační programy, které nemají přímé podpory pro dotaz rozhraní API. Najdete v článku [wiki](https://github.com/Microsoft/vsixbootstrapper/wiki) příklady. |

## <a name="see-also"></a>Viz také

* [Změny nastavení 2017 Visual Studio](https://blogs.msdn.microsoft.com/heaths/2016/09/15/changes-to-visual-studio-15-setup)

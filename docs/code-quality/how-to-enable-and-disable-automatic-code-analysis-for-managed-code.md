---
title: Povolit nebo zakázat analýzu kódu
ms.date: 10/25/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ec0a8a3f04830115d343fcef611cfbd338163395
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551044"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>Postupy: Povolení a zákaz automatické analýzy kódu pro spravovaný kód

Můžete nakonfigurovat (statický) analýzu kódu pro spuštění po každém sestavení spravovaného kódu projektu. Můžete nastavit různé vlastnosti analýzy kódu pro každou konfiguraci sestavení, například ladění a vydání.

Tento článek se vztahuje pouze na starší verze analýzy a ne na živé analýzy kódu pomocí [analyzátorů kódu](roslyn-analyzers-overview.md).

## <a name="to-enable-or-disable-automatic-code-analysis"></a>Povolení nebo zakázání automatické analýzy kódu

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na projekt a zvolte možnost **vlastnosti**.

1. V dialogovém okně Vlastnosti projektu klikněte na kartu **Analýza kódu** .

   > [!TIP]
   > Novější typy projektů, například .NET Core a aplikace .NET Standard, nemají kartu **Analýza kódu** . Starší verze analýzy není pro tyto typy projektů k dispozici, ale můžete získat živou analýzu kódu pomocí [analyzátorů kódu založeného na .NET Compiler Platform](roslyn-analyzers-overview.md). Chcete-li potlačit upozornění z analyzátorů kódu, přečtěte si poznámku na konci tohoto článku.

1. Zadejte typ sestavení v **konfiguraci** a cílovou platformu na **platformě**.

1. Chcete-li povolit nebo zakázat automatickou analýzu kódu, zaškrtněte nebo zrušte zaškrtnutí políčka **Povolit analýzu kódu při sestavení** .

> [!NOTE]
> Zaškrtávací políčko **Povolit analýzu kódu při sestavení** má vliv pouze na starší verzi analýzy. Neovlivňuje [analyzátory kódu založené na .NET Compiler Platform](roslyn-analyzers-overview.md), které se vždycky spouštějí při sestavení, pokud jste je nainstalovali jako balíček NuGet. Pokud chcete vymazat chyby analyzátoru z **Seznam chyb**, můžete potlačit všechna aktuální porušení výběrem možnosti **analyzovat** > **Spustit analýzu kódu a potlačit aktivní problémy** na řádku nabídek. Další informace najdete v tématu [potlačení porušení](use-roslyn-analyzers.md#suppress-violations).

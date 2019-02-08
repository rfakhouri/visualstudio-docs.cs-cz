---
title: Povolení nebo zákaz analýzy kódu
ms.date: 10/25/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 4878c25021d87e91f6a575d11a876d7aac2455d5
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918127"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>Postupy: Povolení a zákaz automatické analýzy kódu pro spravovaný kód

Můžete konfigurovat analýzu kódu (statické) ke spuštění po každém sestavení spravovaný projekt kódu. Můžete nastavení vlastností analýzy pro každou konfiguraci sestavení odlišný kód, například ladění a vydání.

Tento článek se týká pouze statické analýzy kódu a pomocí analýzy není živého kódu [analyzátorů Roslyn kódu](roslyn-analyzers-overview.md).

## <a name="to-enable-or-disable-automatic-code-analysis"></a>K povolení nebo zakázání automatické analýzy kódu

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a klikněte na tlačítko **vlastnosti**.

1. V dialogovém okně vlastností projektu zvolte **analýzy kódu** kartu.

   > [!TIP]
   > Typy novější projektů, jako je .NET Core a .NET Standard aplikace nemáte **analýzy kódu** kartu. Analýza statického kódu není k dispozici pro tyto typy projektů, ale můžete pořád dostat, živé kódu pomocí analýzy [analyzátorů Roslyn kódu](roslyn-analyzers-overview.md). Potlačení upozornění z analyzátorů Roslyn kódu, najdete v poznámce na konci tohoto článku.

1. Zadejte typ sestavení v **konfigurace** a cílovou platformu v **platformy**.

1. K povolení nebo zakázání automatické analýzy kódu, zaškrtněte nebo zrušte zaškrtnutí **povolit analýzu kódu na sestavení** zaškrtávací políčko.

> [!NOTE]
> **Povolit analýzu kódu na sestavení** zaškrtávacího políčka se týká pouze statické analýzy kódu. Nemá vliv [analyzátorů Roslyn kódu](roslyn-analyzers-overview.md), což vždy spustit v sestavení, pokud jste nainstalovali jako balíček NuGet. Pokud chcete vymazat chyby analyzátoru z **seznam chyb**, všechna aktuální porušení pravidel můžete potlačit výběrem **analyzovat** > **spustit analýzu kódu a potlačit aktivní Problémy s** na řádku nabídek. Další informace najdete v tématu [potlačit porušení](use-roslyn-analyzers.md#suppress-violations).

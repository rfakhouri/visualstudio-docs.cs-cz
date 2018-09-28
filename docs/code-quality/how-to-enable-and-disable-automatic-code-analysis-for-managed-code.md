---
title: 'Postupy: Povolení a zákaz automatické analýzy kódu pro spravovaný kód'
ms.date: 09/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 3113143b07ccb6f765cd0cf1735b34be6e952c72
ms.sourcegitcommit: 6672a1e9d135d7e5cca3cceea07c6fe5a0871475
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/28/2018
ms.locfileid: "47443542"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>Postupy: povolení a zákaz automatické analýzy kódu pro spravovaný kód

Můžete konfigurovat analýzu kódu pro spuštění po každém sestavení spravovaný projekt kódu. Můžete nastavení vlastností analýzy pro každou konfiguraci sestavení odlišný kód, například ladění a vydání.

## <a name="to-enable-or-disable-automatic-code-analysis"></a>K povolení nebo zakázání automatické analýzy kódu

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a klikněte na tlačítko **vlastnosti**.

1. V dialogovém okně vlastností projektu zvolte **analýzy kódu** kartu.

1. Zadejte typ sestavení v **konfigurace** a cílovou platformu v **platformy**.

1. K povolení nebo zakázání automatické analýzy kódu, zaškrtněte nebo zrušte zaškrtnutí **povolit analýzu kódu na sestavení** zaškrtávací políčko.

> [!NOTE]
> **Povolit analýzu kódu na sestavení** zaškrtávacího políčka se týká pouze statické analýzy kódu. Nemá vliv [analyzátorů Roslyn kódu](roslyn-analyzers-overview.md), což vždy spustit v sestavení, pokud jste nainstalovali jako balíček NuGet. Pokud chcete vymazat chyby analyzátoru z **seznam chyb**, všechna aktuální porušení pravidel můžete potlačit výběrem **analyzovat** > **spustit analýzu kódu a potlačit aktivní Problémy s** na řádku nabídek. Další informace najdete v tématu [potlačit porušení](use-roslyn-analyzers.md#suppress-violations).

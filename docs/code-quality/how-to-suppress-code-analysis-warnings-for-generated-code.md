---
title: Potlačit porušení zásad analýzy kódu pro kód generovaný
ms.date: 05/13/2019
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6a7990f5e9fa1893d8813b1307ab6a0a7fee46be
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65613567"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>Postupy: Potlačení upozornění analýzy kódu pro vygenerovaný kód

Generovaný kód obsahuje kód, který se přidá do vašeho projektu ve spravovaném kódu kompilátory a nástroje třetích stran. Můžete chtít zobrazit porušení pravidel, které zjistí analýzy kódu v generovaném kódu. Protože nelze zobrazit a spravovat kód, který obsahuje porušení zásad, nemusí však chcete vidět.

**Potlačit Výsledky generovaného kódu** zaškrtávací políčko na stránce vlastností analýzy kódu projektu umožňuje vybrat, jestli se má zobrazit kód upozornění analýzy kódu generovaném nástrojem třetích stran.

> [!NOTE]
> Tato možnost není potlačit chyby analýzy kódu a upozornění z generovaného kódu při chyby a upozornění se zobrazí ve formulářích a šablony. Můžete jak zobrazit a spravovat zdrojový kód pro formuláře nebo šablony.

### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>Potlačit upozornění pro vygenerovaný kód v projektu

1. Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a potom klikněte na tlačítko **vlastnosti**.

2. Zvolte **analýzy kódu** kartu.

3. Vyberte **potlačit Výsledky generovaného kódu** zaškrtávací políčko.

> [!NOTE]
> Pouze můžete potlačit upozornění statické analýzy kódu. V současné době nelze potlačení upozornění analýzy kódu z [analyzátory](roslyn-analyzers-overview.md).
---
title: Potlačit porušení analýzy kódu pro generovaný kód
ms.date: 05/13/2019
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6ee4e3df94e46b4d3cc996a23fc1e40401195e21
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551133"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>Postupy: Potlačení upozornění analýzy kódu pro vygenerovaný kód

Generovaný kód zahrnuje kód, který je přidán do projektu pomocí kompilátorů spravovaného kódu nebo nástrojů třetích stran. Je možné, že budete chtít zobrazit porušení pravidel, která analýza kódu zjistí v generovaném kódu. Vzhledem k tomu, že nemůžete zobrazit a udržovat kód, který obsahuje porušení, možná je nechcete zobrazit.

Zaškrtávací políčko **Potlačit výsledky z vygenerovaného kódu** na stránce vlastností analýza kódu projektu umožňuje vybrat, zda se má zobrazit upozornění analýzy kódu z kódu generovaného nástrojem třetí strany.

> [!NOTE]
> Tato možnost není potlačit chyby analýzy kódu a upozornění z generovaného kódu při chyby a upozornění se zobrazí ve formulářích a šablony. Zdrojový kód formuláře nebo šablony můžete zobrazit a spravovat.

### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>Potlačení upozornění pro generovaný kód v projektu

1. Klikněte pravým tlačítkem na projekt v **Průzkumník řešení** a pak klikněte na **vlastnosti**.

2. Klikněte na kartu **Analýza kódu** .

3. Zaškrtněte políčko **Potlačit výsledky z generovaného kódu** .

> [!NOTE]
> Upozornění můžete potlačit jenom z analýz starší verze. V současné době nemůžete potlačit upozornění [](roslyn-analyzers-overview.md)analýzy kódu z analyzátorů.
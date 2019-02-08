---
title: 'Postupy: Potlačení upozornění analýzy kódu pro vygenerovaný kód'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c0bc46684d94470bb5e12cbdbecb5538ceb89606
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936070"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>Postupy: Potlačení upozornění analýzy kódu pro vygenerovaný kód
Spravovaný kód často vygeneruje kód, který se přidá do projektu k usnadnění vývoje rychlý kód. Kromě toho vývojáři často pomocí nástroje třetích stran vám pomůžou s vývojem aplikací rychle. Tyto nástroje také generovat kód, který je přidán do projektu.

 Můžete chtít zobrazit porušení pravidel, které zjistí analýzy kódu v generovaném kódu. Ale nebudete chtít zobrazovat v případě, že nelze zobrazit a spravovat kód, který obsahuje porušení zásady.

 **Potlačit Výsledky generovaného kódu** zaškrtávací políčko na stránce vlastností analýzy kódu projektu umožňuje vybrat, jestli chcete zobrazit upozornění analýzy kódu v kódu generovaném nástrojem třetích stran.

> [!NOTE]
>  Tato možnost nepotlačuje analýzy kódu chyby a upozornění z generovaného kódu při chyby a upozornění se zobrazí ve formulářích a šablony. Můžete jak zobrazit a spravovat zdrojový kód pro formuláře nebo šablony.

### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>Potlačit upozornění pro vygenerovaný kód v projektu

1.  Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a potom klikněte na tlačítko **vlastnosti**.

2.  Klikněte na tlačítko **analýza kódu**.

3.  Vyberte **potlačit Výsledky generovaného kódu** zaškrtávací políčko.
---
title: 'Postupy: Vynucování udržovatelného kódu pomocí zásady vracení se změnami Analýzy kódu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6269b4839c552fa6a1e982226bbb311cb7d5e9d9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>Postupy: vynucování udržovatelného kódu pomocí zásad vrácení se změnami kódu analýzy

Vývojářům nástroj metriky kódu můžete použít k měření složitosti a udržovatelnosti svůj kód, ale nemohou vyvolat metriky kódu v rámci zásad vrácení se změnami. Můžete ale povolit pravidla analýza kódu, které ověření dodržování standardů metriky kódu kódu a vynutit pravidla prostřednictvím zásad vrácení se změnami. Další informace o metriky kódu najdete v tématu [hodnoty metrik kódu](../code-quality/code-metrics-values.md).

Můžete povolit hloubka dědičnosti, třída spojovací, udržovatelnosti Index a pravidla složitosti vynucování udržovatelného kódu pomocí zásad vrácení se změnami analýzy kódu. Všechny čtyři pravidla nebyly nalezeny v kategorii "Udržovatelnosti pravidla" v editoru zásad analýzy kódu.

Správci verzí pro produkt Team Foundation můžete přidat udržovatelnosti pravidel analýzy kódu pro požadavky zásad vrácení se změnami. Tyto vrácení se změnami, zásady potřeba vývojářům spuštění na základě těchto pravidel změn před zahájením vrácení se změnami analýzy kódu.

## <a name="to-open-the-code-analysis-policy-editor"></a>Otevřete editor zásad analýzy kódu

1. V **Team Explorer**, klikněte pravým tlačítkem na týmový projekt, klikněte na **nastavení projektu Team**a potom klikněte na **správy zdrojového kódu**.

     **Správy zdrojového kódu** zobrazí se dialogové okno.

2. Na **zásad vrácení se změnami** a klikněte na **přidat**.

     **Přidání zásad vrácení se změnami** zobrazí se dialogové okno.

3. V **zásad vrácení se změnami** seznamu, vyberte **analýza kódu** zaškrtněte políčko a potom klikněte na **OK**.

     **Editor zásad analýzy kódu** zobrazí se dialogové okno.

## <a name="to-enable-code-analysis-maintainability-rules"></a>Chcete-li povolit udržovatelnosti pravidel analýzy kódu

1. V **Editor zásad analýzy kódu** dialogovém **nastavení pravidla**, rozbalte **udržovatelnosti pravidla** uzlu.

2. Zaškrtněte políčka pro následující pravidla:

    -   Hloubka dědičnosti: **CA1501 AvoidExcessiveInheritance** – prahová hodnota: upozornění na víc než 5 úrovní do hloubky

    -   Složitost: **CA1502 AvoidExcessiveComplexity** – prahová hodnota: upozornění na více než 25

    -   Index udržovatelnosti: **CA1505 AvoidUnmaintainableCode** – prahová hodnota: upozornění na méně než 20

    -   Párování tříd: **CA1506 AvoidExcessiveClassCoupling** – prahová hodnota: upozornění na více než 80 pro třídu a více než 30 pro metodu

    Kromě toho, pokud chcete pravidlo porušení aby úspěšném sestavení, vyberte **považovat upozornění jako chyba** zaškrtněte políčko vedle popis pravidla.

3. Click **OK**. Nová zásada vrácení se změnami nyní platí pro budoucí vrácení se změnami.

## <a name="see-also"></a>Viz také

- [Hodnoty metrik kódu](../code-quality/code-metrics-values.md)
- [Vytváření a používání zásad vrácení se změnami analýzy kódu](../code-quality/creating-and-using-code-analysis-check-in-policies.md)
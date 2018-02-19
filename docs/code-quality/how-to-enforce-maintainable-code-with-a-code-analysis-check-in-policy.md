---
title: "Postupy: vynucování Udržovatelného kódu pomocí zásad vrácení se změnami kódu Analysis | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7ac4f31d1e93ed648bf2065bbff9dac8800c1d4f
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2018
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>Postupy: Vynucování udržovatelného kódu pomocí zásady vracení se změnami Analýzy kódu

Vývojářům nástroj metriky kódu můžete použít k měření složitosti a udržovatelnosti svůj kód, ale nemohou vyvolat metriky kódu v rámci zásad vrácení se změnami. Můžete ale povolit pravidla analýza kódu, které ověřují dodržování standardů metriky kódu kódu a vynucovat pravidla prostřednictvím zásad vrácení se změnami. Další informace o metriky kódu najdete v tématu [hodnoty metrik kódu](../code-quality/code-metrics-values.md).

Můžete povolit hloubka dědičnosti, třída spojovací, udržovatelnosti Index a pravidla složitosti vynucování udržovatelného kódu pomocí zásad vrácení se změnami analýzy kódu. Všechny čtyři pravidla nebyly nalezeny v kategorii "Udržovatelnosti pravidla" v editoru zásad analýzy kódu.

Správci verzí pro produkt Team Foundation můžete přidat udržovatelnosti pravidel analýzy kódu pro požadavky zásad vrácení se změnami. Tyto vrácení se změnami, zásady potřeba vývojářům spuštění na základě těchto pravidel změn před zahájením vrácení se změnami analýzy kódu.

## <a name="to-open-the-code-analysis-policy-editor"></a>Otevřete Editor zásad analýzy kódu

1 v **Team Explorer**, klikněte pravým tlačítkem na týmový projekt, klikněte na **nastavení projektu Team**a potom klikněte na **správy zdrojového kódu**.

     The **Source Control** dialog box appears.

2.Kliknutím na **zásad vrácení se změnami** a klikněte na **přidat**.

     The **Add Check-in Policy** dialog box appears.

3 ve **zásad vrácení se změnami** seznamu, vyberte **analýza kódu** zaškrtněte políčko a potom klikněte na **OK**.

     The **Code Analysis Policy Editor** dialog box appears.

## <a name="to-enable-code-analysis-maintainability-rules"></a>Chcete-li povolit udržovatelnosti pravidel analýzy kódu

1 v **Editor zásad analýzy kódu** dialogovém **nastavení pravidla**, rozbalte **udržovatelnosti pravidla** uzlu.

2. Zaškrtněte políčka pro následující pravidla:

    -   Hloubka dědičnosti: **CA1501 AvoidExcessiveInheritance** – prahová hodnota: upozornění na víc než 5 úrovní do hloubky

    -   Složitost: **CA1502 AvoidExcessiveComplexity** – prahová hodnota: upozornění na více než 25

    -   Index udržovatelnosti: **CA1505 AvoidUnmaintainableCode** – prahová hodnota: upozornění na méně než 20

    -   Párování tříd: **CA1506 AvoidExcessiveClassCoupling** – prahová hodnota: upozornění na více než 80 pro třídu a více než 30 pro metodu

    Kromě toho, pokud chcete pravidlo porušení aby úspěšném sestavení, vyberte **považovat upozornění jako chyba** zaškrtněte políčko vedle popis pravidla.

3 klikněte na tlačítko **OK**. Nová zásada vrácení se změnami nyní platí pro budoucí vrácení se změnami.

## <a name="see-also"></a>Viz také

[Hodnoty metrik kódu](../code-quality/code-metrics-values.md)
[vytváření a používání zásad vrácení se změnami analýzy kódu](../code-quality/creating-and-using-code-analysis-check-in-policies.md)
---
title: 'CA1801: Zkontrolujte nepoužité parametry'
ms.date: 06/24/2019
ms.topic: reference
f1_keywords:
- AvoidUnusedParameters
- CA1801
- ReviewUnusedParameters
helpviewer_keywords:
- CA1801
- ReviewUnusedParameters
ms.assetid: 5d73545c-e153-4b7c-a7b2-be6bf5aca5be
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f9a0714082e0fce744fe74eaa4e4aefee5a41867
ms.sourcegitcommit: 01c3c9dcade5d913bde2c7efa8c931a7b04e6cd0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2019
ms.locfileid: "67365371"
---
# <a name="ca1801-review-unused-parameters"></a>CA1801: Zkontrolujte nepoužité parametry

|||
|-|-|
|TypeName|ReviewUnusedParameters|
|CheckId|CA1801|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné – Pokud člen není viditelný mimo sestavení, bez ohledu na to, které provedete změnu.<br /><br /> Pevné – Pokud změníte členu, který chcete použít parametr v rámci svého těla.<br /><br /> Rozdělení – odeberte parametr a je viditelný mimo sestavení.|

## <a name="cause"></a>Příčina

Podpis metody obsahuje parametr, který není použit v těle metody.

Toto pravidlo nezkoumá následující druhy metod:

- Metody odkazuje delegáta.

- Metody používané jako obslužné rutiny událostí.

- Metody deklarované s `abstract` (`MustOverride` v jazyce Visual Basic) modifikátor.

- Metody deklarované s `virtual` (`Overridable` v jazyce Visual Basic) modifikátor.

- Metody deklarované s `override` (`Overrides` v jazyce Visual Basic) modifikátor.

- Metody deklarované s `extern` (`Declare` v sadě Visual Studio) modifikátor.

## <a name="rule-description"></a>Popis pravidla

Zkontrolujte parametry v nevirtuálních metodách, které nejsou používány v těle metody, abyste měli jistotu, že nesprávnosti kolem selhání k nim přístup. Nevyužité parametry zvyšují náklady na náklady na údržbu a výkonu.

Porušení tohoto pravidla může někdy odkazovat na implementační chybě v metodě. Například parametr by měl byly použity v těle metody. Potlačení upozornění tohoto pravidla, pokud parametr existuje z důvodu zpětné kompatibility.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, odebrat Nepoužitý parametr (k zásadní změně) nebo pomocí parametru v těle metody (nevýznamných změn).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla:

- Pro dříve dodané kód, pro kterou bude oprava rozbíjející změny.

- Pro `this` parametr ve vlastní metody rozšíření pro <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert?displayProperty=nameWithType>. Funkce <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> třídy jsou statické, takže není nutné pro přístup k `this` parametr v těle metody.

## <a name="example"></a>Příklad

Následující příklad ukazuje dva způsoby. Jedna metoda porušuje pravidlo a jiná metoda splňuje pravidlo.

[!code-csharp[FxCop.Usage.ReviewUnusedParameters#1](../code-quality/codesnippet/CSharp/ca1801-review-unused-parameters_1.cs)]

## <a name="related-rules"></a>Související pravidla

[CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)

[CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

[CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)
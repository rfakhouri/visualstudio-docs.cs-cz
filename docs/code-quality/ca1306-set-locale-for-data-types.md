---
title: 'CA1306: Nastavte národního prostředí pro datové typy'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1306
- SetLocaleForDataTypes
helpviewer_keywords:
- CA1306
- SetLocaleForDataTypes
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47faa5e496585940f61f94bb6dfb0b8d9d70f752
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55932739"
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: Nastavte národního prostředí pro datové typy

|||
|-|-|
|TypeName|SetLocaleForDataTypes|
|CheckId|CA1306|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Metoda nebo konstruktor vytvoří jednu nebo více <xref:System.Data.DataTable?displayProperty=fullName> nebo <xref:System.Data.DataSet?displayProperty=fullName> instance a explicitně nenastavil vlastnost národního prostředí (<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> nebo <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>).

## <a name="rule-description"></a>Popis pravidla
 Národní prostředí určuje prvky prezentace specifické kultury pro data, například formátování použité pro číselné hodnoty, symboly měny a pořadí řazení. Když vytvoříte <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet>, byste měli explicitně nastavit národní prostředí. Ve výchozím nastavení je národní prostředí pro tyto typy aktuální jazykové verze. Pro data, která je uložena v databázi nebo souboru a globálně sdíleny, musí být obvykle nastavena národní prostředí na invariantní jazykovou verzi (<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>). Když data se sdílejí napříč jazykovými verzemi, použití výchozí národní prostředí může způsobit obsah <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet> zobrazí, nebo se nesprávně interpretován.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, explicitně nastavit národní prostředí <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné knihovny nebo aplikací je pro omezené místní cílovou skupinu, nesdílí data nebo ve výchozím nastavení provede požadované chování ve všech podporovaných scénářích potlačit upozornění tohoto pravidla.

## <a name="example"></a>Příklad
 Následující příklad vytvoří dva <xref:System.Data.DataTable> instancí.

 [!code-csharp[FxCop.Globalization.DataTable#1](../code-quality/codesnippet/CSharp/ca1306-set-locale-for-data-types_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Data.DataTable?displayProperty=fullName>
- <xref:System.Data.DataSet?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>
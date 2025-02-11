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
ms.openlocfilehash: 893844741c848bee759f56dd027c9976a21902e8
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922794"
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: Nastavte národního prostředí pro datové typy

|||
|-|-|
|TypeName|SetLocaleForDataTypes|
|CheckId|CA1306|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
Metoda nebo konstruktor vytvořila jednu nebo více <xref:System.Data.DataTable?displayProperty=fullName> instancí <xref:System.Data.DataSet?displayProperty=fullName> nebo neexplicitně nastavila vlastnost locale (<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> nebo <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>).

## <a name="rule-description"></a>Popis pravidla
Národní prostředí Určuje prvky prezentace specifické pro jazykovou verzi pro data, jako je například formátování používané pro číselné hodnoty, symboly měny a pořadí řazení. Při vytváření <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet>by mělo být nastavení národního prostředí explicitně nastaveno. Ve výchozím nastavení je národní prostředí pro tyto typy aktuální jazyková verze. Pro data, která jsou uložena v databázi nebo souboru a jsou sdíleny globálně, by mělo být národní prostředí obvykle nastaveno na invariantní<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>jazykovou verzi (). Když jsou data sdílena napříč kulturami, použití výchozího národního prostředí může způsobit, že <xref:System.Data.DataTable> obsah <xref:System.Data.DataSet> nebo bude správně prezentován nebo interpretován.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, explicitně nastavte národní prostředí pro <xref:System.Data.DataTable> nebo. <xref:System.Data.DataSet>

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Z tohoto pravidla je bezpečné potlačit upozornění, když je knihovna nebo aplikace určena pro omezené místní cílové skupiny, data nejsou sdílena nebo výchozí nastavení vydává požadované chování ve všech podporovaných scénářích.

## <a name="example"></a>Příklad
Následující příklad vytvoří dvě <xref:System.Data.DataTable> instance.

[!code-csharp[FxCop.Globalization.DataTable#1](../code-quality/codesnippet/CSharp/ca1306-set-locale-for-data-types_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Data.DataTable?displayProperty=fullName>
- <xref:System.Data.DataSet?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>
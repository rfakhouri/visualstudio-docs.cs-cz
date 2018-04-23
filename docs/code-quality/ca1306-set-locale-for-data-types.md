---
title: 'CA1306: Nastavte národního prostředí pro datové typy'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d7c95c72978e3828d566598e6076bde904169f4b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: Nastavte národního prostředí pro datové typy
|||
|-|-|
|TypeName|SetLocaleForDataTypes|
|CheckId|CA1306|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Metoda nebo konstruktor vytvořit jeden nebo více <xref:System.Data.DataTable?displayProperty=fullName> nebo <xref:System.Data.DataSet?displayProperty=fullName> instance a explicitně nenastavili vlastnost národního prostředí (<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> nebo <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>).

## <a name="rule-description"></a>Popis pravidla
 Národní prostředí určuje prvky prezentace specifické pro jazykovou verzi pro data, jako je například formátování použít pro číselné hodnoty, tyto symboly a pořadí řazení. Při vytváření <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet>, byste měli explicitně nastavit národní prostředí. Ve výchozím nastavení je národní prostředí pro tyto typy aktuální jazykovou verzi. Pro data, která je uložena v databázi nebo souboru a globálně sdíleny, musí být národní prostředí nastavená normálně na neutrální jazykovou verzi (<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>). Pokud data je sdílet jazykové verze, pomocí výchozí národní prostředí může způsobit obsah <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet> uvedené nebo správně interpretovat.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, národní prostředí pro explicitně nastavit <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné při do knihovny nebo aplikací je pro omezené místní cílovou skupinu, není sdílená data nebo výchozí nastavení dosáhnout požadovaného chování ve všech podporovaných scénářích potlačit upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad vytvoří dvě <xref:System.Data.DataTable> instance.

 [!code-csharp[FxCop.Globalization.DataTable#1](../code-quality/codesnippet/CSharp/ca1306-set-locale-for-data-types_1.cs)]

## <a name="see-also"></a>Viz také
 <xref:System.Data.DataTable?displayProperty=fullName> <xref:System.Data.DataSet?displayProperty=fullName> <xref:System.Globalization.CultureInfo?displayProperty=fullName> <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>
---
title: 'CA1300: Určete MessageBoxOptions'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: bd269b099095326a260da7613bf3c2c402e864be
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62797693"
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300: Určete MessageBoxOptions

|||
|-|-|
|TypeName|SpecifyMessageBoxOptions|
|CheckId|CA1300|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Metoda volá přetížení <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> metodu, která se nedají <xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName> argument.

## <a name="rule-description"></a>Popis pravidla

Chcete-li zobrazit okno se zprávou správně pro jazykové verze, které používají směr čtení zprava doleva, předejte [MessageBoxOptions.RightAlign](<xref:System.Windows.Forms.MessageBoxOptions.RightAlign>) a [MessageBoxOptions.RtlReading](<xref:System.Windows.Forms.MessageBoxOptions.RtlReading>) polím <xref:System.Windows.Forms.MessageBox.Show%2A> Metoda. Zkontrolujte <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName> vlastnost ovládacího prvku obsahujícího k určení, jestli se má použít pořadí čtení zprava doleva.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, zavolejte přetížení <xref:System.Windows.Forms.MessageBox.Show%2A> metodu, která přebírá <xref:System.Windows.Forms.MessageBoxOptions> argument.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, když knihovny kódu nesmí být lokalizována pro jazykovou verzi, která používá pořadí čtení zprava doleva.

## <a name="example"></a>Příklad

Následující příklad ukazuje metodu, která zobrazí okno se zprávou, která obsahuje možnosti, které jsou vhodné pro pořadí čtení jazykové verze. Soubor prostředků, který není zobrazený, je potřeba vytvořit příklad. Postupujte podle komentáře v příkladu, k vytvoření příkladu bez souboru prostředků a otestovat funkci zprava doleva.

[!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
[!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [Prostředky v aplikacích klasické pracovní plochy (.NET Framework)](/dotnet/framework/resources/index)
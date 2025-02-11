---
title: 'CA1305: Určete IFormatProvider'
ms.date: 06/30/2018
ms.topic: reference
f1_keywords:
- SpecifyIFormatProvider
- CA1305
helpviewer_keywords:
- CA1305
- SpecifyIFormatProvider
ms.assetid: fb34ed9a-4eab-47cc-8eef-3068a4a1397e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: eda86085a5a2b8ba8e42116005890d2bda0b1dca
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714687"
---
# <a name="ca1305-specify-iformatprovider"></a>CA1305: Určete IFormatProvider

|||
|-|-|
|TypeName|SpecifyIFormatProvider|
|CheckId|CA1305|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Metoda nebo konstruktor volá jeden nebo více členů, které mají přetížení <xref:System.IFormatProvider?displayProperty=fullName> parametr a tato metoda nebo konstruktor nevolá přetížení přebírající <xref:System.IFormatProvider> parametru.

Toto pravidlo ignoruje volání metod rozhraní .NET, které jsou popsány jako ignoruje <xref:System.IFormatProvider> parametru. Pravidla i ignoruje následujících metod:

- <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>

## <a name="rule-description"></a>Popis pravidla

Když <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> nebo <xref:System.IFormatProvider> objektu není zadán, výchozí hodnota zadaná pomocí přetíženého členu nemusí mít ve všech národních prostředích požadovaný efekt. Kromě toho členy rozhraní .NET zvolte výchozí jazykovou verzi a formátování podle předpokladů, které nemusí být správná pro váš kód. Pokud chcete mít jistotu, že kód funguje podle očekávání pro vaše scénáře, by měla poskytnout informace specifické jazykové verze podle následujících pokynů:

- Pokud uživateli se zobrazí hodnotu, použijte aktuální jazykové verze. Viz <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.

- Pokud hodnota se budou ukládat a přístupný softwarem (trvale uložena do souboru nebo databáze), pomocí neutrální jazykové verze. Viz <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.

- Pokud si nejste jisti cílové hodnoty, mají příjemce dat nebo zprostředkovatele zadejte jazykovou verzi.

I v případě, že výchozí chování přetíženého členu je vhodné pro vaše potřeby, je lepší explicitně volat přetížení specifické pro jazykovou verzi tak, aby váš kód je držitelem dokumentů a snadněji zachována.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, použijte přetížení přijímající <xref:System.IFormatProvider> argument. Nebo můžete použít [jazyka C# interpolovaný řetězec](/dotnet/csharp/tutorials/string-interpolation) a předejte ji do <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, když je jisté, že výchozí formát je správnou volbou a udržovatelnosti kódu není prioritou důležité vývojové.

## <a name="example"></a>Příklad

V následujícím kódu `example1` řetězec porušuje pravidlo CA1305. `example2` Řetězec splňuje pravidlo CA1305 předáním <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>, která implementuje <xref:System.IFormatProvider>do <xref:System.String.Format(System.IFormatProvider,System.String,System.Object)?displayProperty=nameWithType>. `example3` Řetězec splňuje pravidlo CA1305 předáním interpolovaném řetězci na <xref:System.FormattableString.Invariant%2A?displayProperty=fullName]>.

```csharp
string name = "Georgette";

// Violates CA1305
string example1 = String.Format("Hello {0}", name);

// Satisfies CA1305
string example2 = String.Format(CultureInfo.CurrentCulture, "Hello {0}", name);

// Satisfies CA1305
string example3 = FormattableString.Invariant($"Hello {name}");
```

## <a name="related-rules"></a>Související pravidla

- [CA1304: Zadejte možnosti CultureInfo](../code-quality/ca1304-specify-cultureinfo.md)

## <a name="see-also"></a>Viz také:

- [Pomocí třídy CultureInfo](/dotnet/standard/globalization-localization/globalization#work-with-culture-specific-settings)
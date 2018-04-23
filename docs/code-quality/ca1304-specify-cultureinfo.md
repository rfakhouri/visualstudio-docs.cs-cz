---
title: 'CA1304: Zadejte možnosti CultureInfo'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyCultureInfo
- CA1304
helpviewer_keywords:
- SpecifyCultureInfo
- CA1304
ms.assetid: b912d76a-54fd-4c93-b25d-16491e0ae319
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dec38172f65b7b4d828dc96f0b2f51b28ce1ebd6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1304-specify-cultureinfo"></a>CA1304: Zadejte možnosti CultureInfo
|||
|-|-|
|TypeName|SpecifyCultureInfo|
|CheckId|CA1304|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Metoda nebo konstruktor volá člena, který má přetížení, které přijímá <xref:System.Globalization.CultureInfo?displayProperty=fullName> parametr a metoda nebo konstruktor nevolá přetížení, které přijímá <xref:System.Globalization.CultureInfo> parametr. Toto pravidlo ignoruje volání těchto metod:

-   <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>

-   <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=fullName>

-   <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>

## <a name="rule-description"></a>Popis pravidla
 Když <xref:System.Globalization.CultureInfo> nebo <xref:System.IFormatProvider?displayProperty=fullName> objekt není zadaný, výchozí hodnotu, která poskytuje přetížené člen pravděpodobně nemá vliv, který chcete ve všech národních prostředí. Navíc [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] členy zvolte výchozí jazykovou verzi a formátování podle předpoklady, které nemusí být správná pro váš kód. Chcete-li zajistěte, aby byl že kód funguje podle očekávání pro vaše scénáře, musí zadat informace specifické pro jazykovou verzi podle následujících pokynů:

-   Pokud hodnota se zobrazí uživatelům, použijte aktuální jazykovou verzi. V tématu <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>.

-   Pokud hodnota budou uloženy a software používá, tedy trvalé k souboru nebo databáze, použijte neutrální jazykovou verzi. V tématu <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.

-   Pokud si nejste jisti cílové hodnoty, spotřebitele dat nebo zprostředkovatele zadejte jazykovou verzi.

 Všimněte si, že <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> slouží pouze k načíst lokalizované prostředky pomocí instance <xref:System.Resources.ResourceManager?displayProperty=fullName> třídy.

 I když výchozí chování přetížené člen je vhodné pro vaše potřeby, je lepší explicitně volat přetížení specifické pro jazykovou verzi, aby váš kód je automatické protokolování prováděných a snadněji zachována.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, použijte přetížení, které přijímá <xref:System.Globalization.CultureInfo> nebo <xref:System.IFormatProvider> a zadat argument podle pokynů, které byly uvedené výše.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění od tohoto pravidla, když je jisté, že výchozí zprostředkovatel formátu jazykové verze nebo je nejvhodnější a kde udržovatelnost kódu není důležité vývojové prioritou.

## <a name="example"></a>Příklad
 V následujícím příkladu `BadMethod` způsobí, že dvě porušení toto pravidlo. `GoodMethod` vyřeší první porušení pomocí předání System.String.Compare neutrální jazykovou verzi a opravuje druhý porušení předáním aktuální jazykovou verzi, která <xref:System.String.ToLower%2A> protože `string3` se zobrazí uživateli.

 [!code-csharp[FxCop.Globalization.CultureInfo#1](../code-quality/codesnippet/CSharp/ca1304-specify-cultureinfo_1.cs)]

## <a name="example"></a>Příklad
 Následující příklad ukazuje účinek aktuální jazykovou verzi na výchozí <xref:System.IFormatProvider> ve které je vybrán <xref:System.DateTime> typu.

 [!code-csharp[FxCop.Globalization.IFormatProvider#1](../code-quality/codesnippet/CSharp/ca1304-specify-cultureinfo_2.cs)]

 Tento příklad vytvoří následující výstup.

 **6/4/1900 12:15:12: 00**
**06/04/1900 12:15:12**
## <a name="related-rules"></a>Související pravidla
 [CA1305: Zadejte možnosti IFormatProvider](../code-quality/ca1305-specify-iformatprovider.md)

## <a name="see-also"></a>Viz také
[Použití třídy CultureInfo](/dotnet/standard/globalization-localization/globalization#Cultures)
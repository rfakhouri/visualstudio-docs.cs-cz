---
title: 'CA1305: Zadejte možnosti IFormatProvider'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da4125a87ea7fe1576834dacc14af9a1a1861206
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1305-specify-iformatprovider"></a>CA1305: Zadejte možnosti IFormatProvider
|||
|-|-|
|TypeName|SpecifyIFormatProvider|
|CheckId|CA1305|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Metoda nebo konstruktor volání jednoho nebo více členů, které mají přetížení, které přijímají <xref:System.IFormatProvider?displayProperty=fullName> parametr a metoda nebo konstruktor nevolá přetížení, které přijímá <xref:System.IFormatProvider> parametr. Toto pravidlo ignoruje volání [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] metody, které jsou dokumentovány jako ignoruje <xref:System.IFormatProvider> parametr a kromě těchto metod:

-   <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>

-   <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=fullName>

-   <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>

## <a name="rule-description"></a>Popis pravidla
 Když <xref:System.Globalization.CultureInfo?displayProperty=fullName> nebo <xref:System.IFormatProvider> objekt není zadaný, výchozí hodnotu, která poskytuje přetížené člen pravděpodobně nemá vliv, který chcete ve všech národních prostředí. Navíc [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] členy zvolte výchozí jazykovou verzi a formátování podle předpoklady, které nemusí být správná pro váš kód. Chcete-li mít jistotu, že kód funguje podle očekávání pro vaše scénáře, by měl zadat informace specifické pro jazykovou verzi podle následujících pokynů:

-   Pokud hodnota se zobrazí uživatelům, použijte aktuální jazykovou verzi. V tématu <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>.

-   Pokud hodnota bude ukládat a přistupovat softwarem (uchovávané k souboru nebo databáze), použijte neutrální jazykovou verzi. V tématu <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.

-   Pokud si nejste jisti cílové hodnoty, spotřebitele dat nebo zprostředkovatele zadejte jazykovou verzi.

 Všimněte si, že <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> slouží pouze k načíst lokalizované prostředky pomocí instance <xref:System.Resources.ResourceManager?displayProperty=fullName> třídy.

 I když výchozí chování přetížené člen je vhodné pro vaše potřeby, je lepší explicitně volat přetížení specifické pro jazykovou verzi, aby váš kód je automatické protokolování prováděných a snadněji zachována.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, použijte přetížení, které přijímá <xref:System.Globalization.CultureInfo> nebo <xref:System.IFormatProvider> a zadat argument podle pokynů, které byly uvedené výše.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, když je jisté, že výchozí zprostředkovatel formátu jazykové verze nebo je nejvhodnější a které udržovatelnost kódu není důležité vývojové priority.

## <a name="example"></a>Příklad
 V následujícím příkladu `BadMethod` způsobí, že dvě porušení toto pravidlo. `GoodMethod` vyřeší první porušení předáním neutrální jazykovou verzi, která <xref:System.String.Compare%2A>a opravuje druhý porušení předáním aktuální jazykovou verzi, která <xref:System.String.ToLower%2A> protože `string3` se zobrazí uživateli.

 [!code-csharp[FxCop.Globalization.CultureInfo#1](../code-quality/codesnippet/CSharp/ca1305-specify-iformatprovider_1.cs)]

## <a name="example"></a>Příklad
 Následující příklad ukazuje účinek aktuální jazykovou verzi na výchozí <xref:System.IFormatProvider> ve které je vybrán <xref:System.DateTime> typu.

 [!code-csharp[FxCop.Globalization.IFormatProvider#1](../code-quality/codesnippet/CSharp/ca1305-specify-iformatprovider_2.cs)]

 Tento příklad vytvoří následující výstup.

 **6/4/1900 12:15:12: 00**
**06/04/1900 12:15:12**
## <a name="related-rules"></a>Související pravidla
 [CA1304: Zadejte možnosti CultureInfo](../code-quality/ca1304-specify-cultureinfo.md)

## <a name="see-also"></a>Viz také
[Použití třídy CultureInfo](/dotnet/standard/globalization-localization/globalization#Cultures)
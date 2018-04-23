---
title: 'CA1045: Nepředávejte typy odkazem'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1045
- DoNotPassTypesByReference
helpviewer_keywords:
- CA1045
- DoNotPassTypesByReference
ms.assetid: bcc3900a-e092-4bb8-896f-cb83f6289968
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bb4d43c5715b524582ceb278396885b7df3280ca
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1045-do-not-pass-types-by-reference"></a>CA1045: Nepředávejte typy odkazem
|||
|-|-|
|TypeName|DoNotPassTypesByReference|
|CheckId|CA1045|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Má metoda veřejných nebo chráněné v veřejného typu `ref` parametr, který přebírá primitivní typ, odkazového typu nebo typ hodnoty, který není jedním z předdefinovaných typů.

## <a name="rule-description"></a>Popis pravidla
 Předání typů podle reference (pomocí `out` nebo `ref`) vyžaduje zkušenosti s ukazatele, pochopení, jak se liší typy hodnot a typy odkazu a zpracování metody, které mají více vrácených hodnot. Navíc rozdíl mezi `out` a `ref` parametry nebyl pochopen široce.

 Když odkazového typu předána "odkazem", metodu v úmyslu použít parametr a vracet různé instanci objektu. (Předávání typu odkazu odkazem se taky říká pomocí dvojité ukazatel, ukazatel na ukazatel nebo dvojité indirection.) Pomocí výchozího konvence, což je předat "hodnotou", volání obdrží parametr, který již má odkaz na typ ukazatele na objekt. Ukazatele, není objekt, na kterou odkazuje, je předaná hodnota. Předání hodnotou znamená, že metoda nelze změnit ukazatele jej přejděte na novou instanci třídy odkaz na typ, ale můžete změnit obsah objektu, na kterou odkazuje. Pro většinu aplikací je dostačující a chování, které chcete dosáhnout.

 Pokud metoda musí vracet jinou instanci, použijte k tomu návratovou hodnotu metody. Najdete v článku <xref:System.String?displayProperty=fullName> třídu pro celou řadu metod, které pracují řetězce a vrátí novou instanci třídy řetězec. Pomocí tohoto modelu je ponechán volajícímu se rozhodnout, jestli se zachová, i původní objekt.

 I když návratové hodnoty jsou běžné a zatížen správné použití `out` a `ref` parametry vyžaduje zprostředkující návrhu a znalosti kódování. Knihovna architektům, kteří návrhu pro obecné cílové skupiny by neměl očekávat uživatelům hlavní práci s `out` nebo `ref` parametry.

> [!NOTE]
>  Při práci s parametry, které jsou velké struktury další prostředky, které jsou nutné ke zkopírování těchto struktur může způsobit nežádoucí vliv výkon při předání hodnotou. V těchto případech můžete zvážit použití `ref` nebo `out` parametry.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, která je způsobena typ hodnoty, máte metoda vrátí objekt jako hodnoty. Pokud metoda musí vrátit více hodnot, změnit návrh ho vrátit do jedné instance objekt, který obsahuje hodnoty.

 Chcete-li opravit porušení tohoto pravidla, která způsobuje odkazového typu, ujistěte se, že chování, které chcete, aby se vrátí novou instanci třídy odkaz na. Pokud se jedná, metoda by k tomu použít hodnoty.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo; Tento návrh však může způsobit problémy se použitelnost.

## <a name="example"></a>Příklad
 Následující knihovny ukazuje dva implementace třídy, která generuje odpovědi na zpětné vazby uživatele. První implementace (`BadRefAndOut`) vynutí knihovny uživatelům spravovat tři návratové hodnoty. Druhý implementace (`RedesignedRefAndOut`) zjednodušuje uživatelské prostředí tím, že vrací instanci třídy kontejneru (`ReplyData`), spravuje data jako na jednu jednotku.

 [!code-csharp[FxCop.Design.NoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_1.cs)]

## <a name="example"></a>Příklad
 Následující aplikace znázorňuje činnost koncového uživatele. Volání přepracovanou knihovny (`UseTheSimplifiedClass` metoda) je více jasné, a informace, které je vrácená metodou je snadno spravovat. Výstup z tyto dvě metody se shoduje.

 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_2.cs)]

## <a name="example"></a>Příklad
 Knihovně následující příklad ukazuje, jak `ref` parametry pro odkazové typy se používají a zobrazuje lepší způsob, jak implementovat tuto funkci.

 [!code-csharp[FxCop.Design.RefByRefNo#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_3.cs)]

## <a name="example"></a>Příklad
 Následující aplikace volá jednotlivých metod v knihovně k předvedení chování.

 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_4.cs)]

 Tento příklad vytvoří následující výstup.

 **Změna ukazatele - předaná hodnota:**
**12345**
**12345**
**změna ukazatele - předání odkazem:** 
 ** 12345**
**12345 ABCDE**
**předání návratovou hodnotu:**
**12345 ABCDE**
## <a name="related-rules"></a>Související pravidla
 [CA1021: Vyhněte se výstupním parametrům](../code-quality/ca1021-avoid-out-parameters.md)
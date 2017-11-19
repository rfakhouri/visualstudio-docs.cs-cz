---
title: "CA1021: Vyhněte se parametry | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1021
- AvoidOutParameters
helpviewer_keywords:
- AvoidOutParameters
- CA1021
ms.assetid: 970f2304-842c-4fb7-9734-f3871da8d479
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: dbefcb83efbcea76fec889b520f0cd0dd181bf9e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1021-avoid-out-parameters"></a>CA1021: Vyhněte se výstupním parametrům
|||  
|-|-|  
|TypeName|AvoidOutParameters|  
|CheckId|CA1021|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Metoda veřejných nebo chráněné v veřejného typu má `out` parametr.  
  
## <a name="rule-description"></a>Popis pravidla  
 Předání typů podle reference (pomocí `out` nebo `ref`) vyžaduje zkušenosti s ukazatele, pochopení, jak se liší typy hodnot a typy odkazu a zpracování metod s více vrácených hodnot. Navíc rozdíl mezi `out` a `ref` parametry nebyl pochopen široce.  
  
 Když odkazového typu předána "odkazem", metodu v úmyslu použít parametr a vracet různé instanci objektu. Předání typu odkazu odkazem se označuje také jako pomocí dvojité ukazatel, ukazatel na ukazatel nebo dvojité indirection. Pomocí výchozí konvence, což je předat "hodnotou", volání obdrží parametr, který již má odkaz na typ ukazatele na objekt. Ukazatele, není objekt, na kterou odkazuje, je předaná hodnota. Předejte podle hodnota znamená, že metoda nelze změnit ukazatele jej přejděte do nové instance typu odkazu. Můžete ji však změnit obsah objektu, na kterou odkazuje. Pro většinu aplikací je dostačující a dosáhnout požadovaného chování.  
  
 Pokud metoda musí vracet jinou instanci, použijte k tomu návratovou hodnotu metody. Najdete v článku <xref:System.String?displayProperty=fullName> třídu pro celou řadu metod, které pracují řetězce a vrátí novou instanci třídy řetězec. Když tento model se používá, volající musíte rozhodnout, jestli se zachová, i původní objekt.  
  
 I když návratové hodnoty jsou běžné a zatížen správné použití `out` a `ref` parametry vyžaduje zprostředkující návrhu a znalosti kódování. Knihovna architektům, kteří návrhu pro obecné cílové skupiny by neměl očekávat uživatelům hlavní práci s `out` nebo `ref` parametry.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, která je způsobena typ hodnoty, máte metoda vrátí objekt jako hodnoty. Pokud metoda musí vrátit více hodnot, změnit návrh ho vrátit do jedné instance objekt, který obsahuje hodnoty.  
  
 Opravit porušení tohoto pravidla, která způsobuje odkazového typu, ujistěte se, že se vrátí novou instanci třídy odkaz na toto chování žádoucí. Pokud se jedná, metoda by k tomu použít hodnoty.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné upozornění toto pravidlo potlačit. Tento návrh však může způsobit problémy se použitelnost.  
  
## <a name="example"></a>Příklad  
 Následující knihovny ukazuje dva implementace třídy, která generuje odpovědi na zpětné vazby uživatele. První implementace (`BadRefAndOut`) vynutí knihovny uživatelům spravovat tři návratové hodnoty. Druhý implementace (`RedesignedRefAndOut`) zjednodušuje uživatelské prostředí tím, že vrací instanci třídy kontejneru (`ReplyData`), spravuje data jako na jednu jednotku.  
  
 [!code-csharp[FxCop.Design.NoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující aplikace znázorňuje činnost koncového uživatele. Volání přepracovanou knihovny (`UseTheSimplifiedClass` metoda) je více jasné, a je snadno spravovat vrácené metodou informace. Výstup z tyto dvě metody se shoduje.  
  
 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_2.cs)]  
  
## <a name="example"></a>Příklad  
 Knihovně následující příklad ukazuje, jak `ref` parametry pro odkazové typy se používají a ukazuje lepší způsob, jak implementovat tuto funkci.  
  
 [!code-csharp[FxCop.Design.RefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_3.cs)]  
  
## <a name="example"></a>Příklad  
 Následující aplikace volá jednotlivých metod v knihovně k předvedení chování.  
  
 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_4.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **Změna ukazatele - předaná hodnota:**  
**12345**  
**12345**  
**Změna ukazatele - předání odkazem:**  
**12345**  
**12345 ABCDE**  
**Předání návratovou hodnotu:**  
**12345 ABCDE**   
## <a name="try-pattern-methods"></a>Zkuste vzor metody  
  
### <a name="description"></a>Popis  
 Metody, které implementují **zkuste\<něco >** vzor, jako například <xref:System.Int32.TryParse%2A?displayProperty=fullName>, není vyvolat tento porušení. Následující příklad ukazuje strukturu (typ hodnoty), která implementuje <xref:System.Int32.TryParse%2A?displayProperty=fullName> metoda.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.TryPattern#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_5.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1045: Nepředávejte typy odkazem](../code-quality/ca1045-do-not-pass-types-by-reference.md)
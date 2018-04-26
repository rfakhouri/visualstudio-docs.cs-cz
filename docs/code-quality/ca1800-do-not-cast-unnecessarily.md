---
title: 'CA1800: Nepřetypujte zbytečně'
ms.date: 10/26/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 34c03adb8ff34d3590ed93264d77536c4cdff080
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800: Nepřetypujte zbytečně
|||
|-|-|
|TypeName|DoNotCastUnnecessarily|
|CheckId|CA1800|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
Metoda provádí duplicitní položky CAST u jednoho z jeho argumentů nebo lokální proměnné.

Pro dokončení analýzy tímto pravidlem otestovaný sestavení musí být vytvořené pomocí informace o ladění a přidružené programového souboru databáze (.pdb) musí být k dispozici.

## <a name="rule-description"></a>Popis pravidla
Duplicitní přetypování snižuje výkon, zvláště když jsou přetypování vykonána v příkazech kompaktní iterace. Pro operace explicitní přetypování duplicitní uložit výsledek přetypování v místní proměnné a použít místní proměnné místo operace duplicitní přetypování.

Pokud jazyka C# `is` operátor slouží k otestování, jestli přetypování bude úspěšné před skutečným přetypování provádí, vezměte v úvahu testování výsledku `as` operátor místo. To poskytuje stejné funkce bez implicitní přetypování operace, které se provádí pomocí `is` operátor. Nebo v C# 7.0 nebo novější, použijte `is` operátor s [porovnávání vzorů](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) ke kontrole převodu typu a přetypování výraz, který se proměnné daného typu v jednom kroku.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, upravte implementace metod, chcete-li minimalizovat počet operací přetypování.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné upozornění toto pravidlo potlačit nebo ignorovat pravidlo úplně, pokud výkon není důležité.

## <a name="examples"></a>Příklady
 Následující příklad ukazuje metodu, která porušuje pravidlo pomocí jazyka C# `is` operátor. Druhé metody splňuje pravidlo nahrazením `is` operátor s testu proti výsledek `as` operátor, který snižuje počet operací přetypování za iteraci ze dvou na jedno. Třetí metoda také splňuje pravidlo s použitím `is` s [porovnávání vzorů](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) vytvoření proměnné požadovaného typu, pokud by úspěšné převod typů.

 [!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_1.cs)]

 Následující příklad ukazuje metodu, `start_Click`, který má více duplicitní explicitní přetypování, která porušuje pravidlo a metodu, `reset_Click`, který splňuje pravidlo uložením přetypování v místní proměnné.

 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/VisualBasic/ca1800-do-not-cast-unnecessarily_2.vb)]
 [!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_2.cs)]

## <a name="see-also"></a>Viz také
[jako (referenční dokumentace jazyka C#)](/dotnet/csharp/language-reference/keywords/as)
[je (referenční dokumentace jazyka C#)](/dotnet/csharp/language-reference/keywords/is)
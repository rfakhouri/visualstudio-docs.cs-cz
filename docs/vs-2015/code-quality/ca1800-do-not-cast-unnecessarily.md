---
title: 'CA1800: Nepřetypujte zbytečně | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 49ffc66b1b7047c7b88664ac0c5198fbd51c51c6
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65682079"
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800: Nepřetypujte zbytečně
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotCastUnnecessarily|
|CheckId|CA1800|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Metoda provádí duplicitní přetypování na jednom z jeho argumenty nebo místní proměnné. Pro dokončení analýzy tímto pravidlem testované sestavení musí být sestaveny s použitím informací o ladění a přidružené programového souboru databáze (PDB) musí být k dispozici.

## <a name="rule-description"></a>Popis pravidla
 Duplicitní přetypování snižuje výkon, zvláště když jsou přetypování vykonána v příkazech kompaktní iterace. Pro explicitní přetypování. duplicitní operace uložení výsledku přetypování do místní proměnné a používat místní proměnnou místo operací duplicitní přetypování.

 Pokud jazyka C# `is` operátor se používá k ověření, zda přetypování proběhne úspěšně, před provedením skutečné přetypování, vezměte v úvahu bude testování výsledku `as` operátor místo toho. Funkce bez implicitní přetypování operace prováděné `is` operátor.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, upravte implementace metody, chcete-li minimalizovat počet operací přetypování.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné, můžete potlačit upozornění tohoto pravidla nebo ignorovat pravidlo úplně, pokud výkon není žádný problém.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která porušuje pravidlo pomocí jazyka C# `is` operátor. Druhá metoda splňuje pravidlo tak, že nahradíte `is` operátor s testují splnění výsledek `as` operátor, který snižuje počet operací přetypování na iteraci ze dvou do jednoho.

 [!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCastsAsIs/cs/FxCop.Performance.UnnecessaryCastsAsIs.cs#1)]

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, `start_Click`, který má více duplicitních explicitní přetypování, který porušuje pravidla a metodu, `reset_Click`, který splňuje pravidlo uložením přetypování do místní proměnné.

 [!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCasts/cs/FxCop.Performance.UnnecessaryCasts.cs#1)]
 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCasts/vb/FxCop.Performance.UnnecessaryCasts.vb#1)]

## <a name="see-also"></a>Viz také
 [jako](https://msdn.microsoft.com/library/a9be126b-cbf4-4990-a70d-d0e1983cad0e) [je](https://msdn.microsoft.com/library/bc62316a-d41f-4f90-8300-c6f4f0556e43)

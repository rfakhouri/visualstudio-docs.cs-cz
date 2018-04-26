---
title: 'CA1011: Zvažte předání základních typů jako parametrů'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1eaa68b6046fd2d3cfb6370b18de2b478b16db9d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: Zvažte předání základních typů jako parametrů
|||
|-|-|
|TypeName|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Deklarace metody obsahuje formální parametr, který je odvozený typ, a volá metodu pouze členové základní typ parametru.

## <a name="rule-description"></a>Popis pravidla
 Je-li v deklaraci metody zadán jako parametr základní typ, lze jako příslušný argument k metodě předat kterýkoliv typ odvozený z tohoto základního typu. Pokud se použije argument uvnitř těla metody, konkrétní metody, která se spustí, závisí na typu argumentu. Pokud není potřeba další funkce, které poskytuje odvozený typ, použijte základní typ umožňuje širší využití metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, změňte typ parametru na jeho základní typ.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění od tohoto pravidla

-   Pokud metoda vyžaduje, aby určitých funkcí, které poskytuje odvozený typ

     \- nebo –

-   vynutit pouze odvozený typ, nebo více odvozený typ, je předaná metodě.

 V těchto případech bude kód robustnější kvůli kontrola silné typ, který je poskytován kompilátoru a modulu runtime.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, `ManipulateFileStream`, který lze použít pouze s <xref:System.IO.FileStream> objekt, který je v rozporu toto pravidlo. Druhá metoda `ManipulateAnyStream`, splňuje pravidlo nahrazením <xref:System.IO.FileStream> parametr pomocí <xref:System.IO.Stream>.

 [!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CSharp/ca1011-consider-passing-base-types-as-parameters_1.cs)]
 [!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CPP/ca1011-consider-passing-base-types-as-parameters_1.cpp)]
 [!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1011-consider-passing-base-types-as-parameters_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1059: Členové by neměli zveřejňovat určité konkrétní typy](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)
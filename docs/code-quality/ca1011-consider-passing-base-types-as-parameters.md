---
title: 'CA1011: Zvažte předání základních typů jako parametrů'
ms.date: 11/04/2016
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
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 644c581757a559311b6660a77c4d9190a7361314
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779544"
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: Zvažte předání základních typů jako parametrů

|||
|-|-|
|TypeName|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Deklarace metody obsahuje formální parametr, který je odvozený typ a metodu volá pouze členy základního typu parametru.

## <a name="rule-description"></a>Popis pravidla

Je-li v deklaraci metody zadán jako parametr základní typ, lze jako příslušný argument k metodě předat kterýkoliv typ odvozený z tohoto základního typu. Pokud argument je použit uvnitř těla metody, konkrétní metody, která se spustí záviset na typu argumentu. Pokud je další funkce, která je poskytována odvozený typ není vyžadována, umožňuje použití základního typu širší využití metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, změňte na jeho základní typ typu parametru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla

- Pokud metoda vyžaduje konkrétní funkce, která je poskytována odvozený typ

     \- nebo –

- k vynucení pouze odvozený typ, nebo více odvozeného typu, je předán metodě.

V takových případech bude kód robustnější kvůli silný typ kontroly, které poskytuje kompilátoru a modulu runtime.

## <a name="example"></a>Příklad

Následující příklad ukazuje metodu, `ManipulateFileStream`, který jde použít jenom s <xref:System.IO.FileStream> objektu, který porušuje tato pravidla. Druhá metoda `ManipulateAnyStream`, splňuje pravidlo tak, že nahradíte <xref:System.IO.FileStream> parametr pomocí <xref:System.IO.Stream>.

[!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CSharp/ca1011-consider-passing-base-types-as-parameters_1.cs)]
[!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CPP/ca1011-consider-passing-base-types-as-parameters_1.cpp)]
[!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1011-consider-passing-base-types-as-parameters_1.vb)]

## <a name="related-rules"></a>Související pravidla

[CA1059: Členy by neměly zveřejňovat určité konkrétní typy](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)
---
title: 'CA2136: Členy by neměly mít konfliktní poznámky transparentnosti'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b73148800c60280ed72e0d5f8014cfe6b97d217
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62542206"
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: Členy by neměly mít konfliktní poznámky transparentnosti

|||
|-|-|
|TypeName|TransparencyAnnotationsShouldNotConflict|
|CheckId|CA2136|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Toto pravidlo je vyvoláno, když typ člena je označena <xref:System.Security> atribut zabezpečení, který má jiný transparentnost než hodnota atributu zabezpečení kontejneru člena.

## <a name="rule-description"></a>Popis pravidla
 Atributy transparentnosti jsou použity z prvků kódu většího rozsahu na prvky menšího rozsahu. Atributy transparentnosti prvků kódu, které mají větší rozsah, mají přednost před atributy transparentnosti prvků kódu, které jsou obsaženy v prvním prvku. Například třída, která je označena <xref:System.Security.SecurityCriticalAttribute> atributu nesmí obsahovat metodu, která je označena <xref:System.Security.SecuritySafeCriticalAttribute> atribut.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud chcete vyřešit toto porušení, odeberte atribut zabezpečení z elementu kódu, který má menší rozsah nebo změnit jeho atribut být stejné jako nadřazeného elementu kódu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla.

## <a name="example"></a>Příklad
 V následujícím příkladu je označené metodu <xref:System.Security.SecuritySafeCriticalAttribute> atribut a je členem třídy, která je označena <xref:System.Security.SecurityCriticalAttribute> atribut. Bezpečné atribut zabezpečení byste měli odebrat.

 [!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../code-quality/codesnippet/CSharp/ca2136-members-should-not-have-conflicting-transparency-annotations_1.cs)]
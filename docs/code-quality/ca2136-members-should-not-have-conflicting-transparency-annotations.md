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
ms.openlocfilehash: 1dcef8fbfd61b8cd8c946f76d6fcb93dc46f1654
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920633"
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: Členy by neměly mít konfliktní poznámky transparentnosti

|||
|-|-|
|TypeName|TransparencyAnnotationsShouldNotConflict|
|CheckId|CA2136|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Toto pravidlo je vyvoláno, když je člen typu <xref:System.Security> označen atributem zabezpečení, který má odlišnou průhlednost než atribut zabezpečení kontejneru člena.

## <a name="rule-description"></a>Popis pravidla
Atributy transparentnosti jsou použity z prvků kódu většího rozsahu na prvky menšího rozsahu. Atributy transparentnosti prvků kódu, které mají větší rozsah, mají přednost před atributy transparentnosti prvků kódu, které jsou obsaženy v prvním prvku. Například třída, která je označena <xref:System.Security.SecurityCriticalAttribute> atributem, nesmí obsahovat metodu, která je označena <xref:System.Security.SecuritySafeCriticalAttribute> atributem.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li toto porušení opravit, odeberte atribut zabezpečení z prvku kódu, který má nižší rozsah, nebo změňte jeho atribut tak, aby byl stejný jako element obsahující prvek kódu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačit upozornění z tohoto pravidla

## <a name="example"></a>Příklad
V následujícím příkladu je metoda označena <xref:System.Security.SecuritySafeCriticalAttribute> atributem a je členem třídy, která je označena <xref:System.Security.SecurityCriticalAttribute> atributem. Je nutné odebrat atribut zabezpečení Safe.

[!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../code-quality/codesnippet/CSharp/ca2136-members-should-not-have-conflicting-transparency-annotations_1.cs)]
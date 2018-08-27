---
title: 'CA2136: Členy nesmějí mít konfliktní poznámky transparentnosti | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c72cdce9364b20e40033f4920bfde69b760f0f9b
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902965"
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: Členy nesmějí mít konfliktní poznámky transparentnosti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2136: členy nesmějí mít konfliktní poznámky transparentnosti](https://docs.microsoft.com/visualstudio/code-quality/ca2136-members-should-not-have-conflicting-transparency-annotations).

|||
|-|-|
|TypeName|TransparencyAnnotationsShouldNotConflict|
|CheckId|CA2136|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Toto pravidlo je vyvoláno, když typ člena je označena <xref:System.Security> atribut zabezpečení, který má jiný transparentnost než hodnota atributu zabezpečení kontejneru člena.

## <a name="rule-description"></a>Popis pravidla
 Atributy transparentnosti jsou použity z prvků kódu většího rozsahu na prvky menšího rozsahu. Atributy transparentnosti prvků kódu, které mají větší rozsah, mají přednost před atributy transparentnosti prvků kódu, které jsou obsaženy v prvním prvku. Například třída, která je označena <xref:System.Security.SecurityCriticalAttribute> atributu nesmí obsahovat metodu, která je označena <xref:System.Security.SecuritySafeCriticalAttribute> atribut.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud chcete vyřešit toto porušení, odeberte atribut zabezpečení z elementu kódu, který má menší rozsah nebo změnit jeho atribut být stejné jako nadřazeného elementu kódu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla.

## <a name="example"></a>Příklad
 V následujícím příkladu je označené metodu <xref:System.Security.SecuritySafeCriticalAttribute> atribut a je členem třídy, která je označena <xref:System.Security.SecurityCriticalAttribute> atribut. Bezpečné atribut zabezpečení byste měli odebrat.

 [!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2136.transparencyannotationsshouldnotconflict/cs/ca2136 - transparencyannotationsshouldnotconflict.cs#1)]




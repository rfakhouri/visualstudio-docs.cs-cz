---
title: 'CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 852ca3d81b2dc72e4f0cb518a002b746a77cf5e3
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/01/2018
ms.locfileid: "47860157"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen
|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Názvy dva typy, členy, parametry nebo plně kvalifikovaný obory názvů jsou identické, když jsou převedeny na malá písmena.

## <a name="rule-description"></a>Popis pravidla
 Identifikátory pro obory názvů, typy, členy a parametry nelze odlišit pouze ve velikosti písmen, protože jazyky cílené na modul CLR (Common Language Runtime) nemusí rozlišovat malá a velká písmena. Například [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] je často používaný jazyk velká a malá písmena.

 Toto pravidlo je vyvoláno na veřejně viditelné pouze členy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Vyberte název, který je jedinečný, je porovnání pro jiné identifikátory písmen.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Knihovny nemusí být použitelná ve všech jazycích k dispozici v rozhraní .NET Framework.

## <a name="example-of-a-violation"></a>Příkladem porušení
 Následující příklad ukazuje porušení tohoto pravidla.

 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
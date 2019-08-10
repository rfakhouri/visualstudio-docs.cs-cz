---
title: 'CA2243: Řetězcové literály atributů by se měly správně parsovat'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2243
- AttributeStringLiteralsShouldParseCorrectly
helpviewer_keywords:
- AttributeStringLiteralsShouldParseCorrectly
- CA2243
ms.assetid: bfadb366-379d-4ee4-b17b-c4a09bf1106b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f9c0f078c21de023b1f5cfacde0cf122c179adb2
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919903"
---
# <a name="ca2243-attribute-string-literals-should-parse-correctly"></a>CA2243: Řetězcové literály atributů by se měly správně parsovat

|||
|-|-|
|TypeName|AttributeStringLiteralsShouldParseCorrectly|
|CheckId|CA2243|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina
Parametr řetězcového literálu atributu se neanalyzuje správně pro adresu URL, identifikátor GUID nebo verzi.

## <a name="rule-description"></a>Popis pravidla
Vzhledem k tomu, že <xref:System.Attribute?displayProperty=fullName>atributy jsou odvozeny z a jsou použity atributy v době kompilace, lze do jejich konstruktorů předat pouze konstantní hodnoty. Parametry atributů, které musí představovat adresy URL, identifikátory GUID a verze, nelze zadat <xref:System.Uri?displayProperty=fullName>jako <xref:System.Guid?displayProperty=fullName>konstanty <xref:System.Version?displayProperty=fullName>, a, protože tyto typy nemohou být reprezentovány jako konstanty. Místo toho musí být reprezentovány pomocí řetězců.

Vzhledem k tomu, že parametr je zadán jako řetězec, je možné předat nesprávně naformátovaný parametr v době kompilace.

Toto pravidlo používá heuristické pojmenování k nalezení parametrů, které reprezentují identifikátor URI (Uniform Resource Identifier), globálně jedinečného identifikátoru (GUID) nebo verzi a ověřuje, že je předaná hodnota správná.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Změňte řetězec parametru na správně vytvořenou adresu URL, identifikátor GUID nebo verzi.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Pokud parametr nepředstavuje adresu URL, identifikátor GUID ani verzi, je bezpečné potlačit upozornění od tohoto pravidla.

## <a name="example"></a>Příklad
Následující příklad ukazuje kód pro AssemblyFileVersionAttribute, který porušuje toto pravidlo.

[!code-csharp[FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly#1](../code-quality/codesnippet/CSharp/ca2243-attribute-string-literals-should-parse-correctly_1.cs)]

Pravidlo se aktivuje následujícími parametry:

- Parametry obsahující ' Version ' a nelze je analyzovat na System. Version.

- Parametry obsahující identifikátor GUID a nelze je analyzovat na System. GUID.

- Parametry obsahující ' URI ', ' urn ' nebo ' URL ' a nelze je analyzovat na System. URI.

## <a name="see-also"></a>Viz také:

- [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)
---
title: 'CA2243: Literály řetězce atributu by se měly správně analyzovat'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6aa6fe4cf38d89e76fc7151f493aac414179064
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2243-attribute-string-literals-should-parse-correctly"></a>CA2243: Literály řetězce atributu by se měly správně analyzovat
|||
|-|-|
|TypeName|AttributeStringLiteralsShouldParseCorrectly|
|CheckId|CA2243|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Parametr literálu řetězce atributu není správně analyzovat pro adresu URL, identifikátor GUID nebo verzi.

## <a name="rule-description"></a>Popis pravidla
 Vzhledem k tomu, že atributy, které jsou odvozeny od <xref:System.Attribute?displayProperty=fullName>a atributy se používají v době kompilace, pouze konstantní hodnoty se dá předat do jejich konstruktory. Atribut parametry, které musí představovat adresy URL, identifikátory GUID a verze nemůže být zadán jako <xref:System.Uri?displayProperty=fullName>, <xref:System.Guid?displayProperty=fullName>, a <xref:System.Version?displayProperty=fullName>, protože tyto typy nemůže být reprezentován jako konstanty. Místo toho se musí být reprezentované pomocí řetězce.

 Protože parametr je zadán jako řetězec, je možné, že nesprávně naformátovanou parametr může být předána v době kompilace.

 Toto pravidlo používá k nalezení parametry, které představují identifikátor URI (URI), globálně jedinečný identifikátor (GUID) nebo verze pojmenování Heuristika a ověří, zda předaná hodnota správná.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Změňte řetězec parametrů k správně vytvořená adresa URL, GUID nebo verze.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, je-li parametr nepředstavuje adresu URL, identifikátor GUID nebo verzi.

## <a name="example"></a>Příklad
 Následující příklad ukazuje kód pro AssemblyFileVersionAttribute, která porušuje toto pravidlo.

 [!code-csharp[FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly#1](../code-quality/codesnippet/CSharp/ca2243-attribute-string-literals-should-parse-correctly_1.cs)]

 Pravidlo se aktivuje následující:

-   Parametry, které obsahují 'version' a nelze analyzovat System.Version.

-   Parametry, které obsahují guid.' a System.Guid nelze analyzovat.

-   Parametry, které obsahují 'uri', 'urn' nebo 'adresy url' a na System.Uri nelze analyzovat.

## <a name="see-also"></a>Viz také
 [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)
---
title: 'CA2243: Literály řetězce atributu by se měly správně analyzovat. | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2243
- AttributeStringLiteralsShouldParseCorrectly
helpviewer_keywords:
- AttributeStringLiteralsShouldParseCorrectly
- CA2243
ms.assetid: bfadb366-379d-4ee4-b17b-c4a09bf1106b
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f23db8a9674de621090be70067a555ef4fca2b99
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201502"
---
# <a name="ca2243-attribute-string-literals-should-parse-correctly"></a>CA2243: Řetězcové literály atributů by se měly správně parsovat
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AttributeStringLiteralsShouldParseCorrectly|
|CheckId|CA2243|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Parametr literál řetězce atributu nesprávně analyzuje adresu URL, identifikátor GUID nebo verzi.

## <a name="rule-description"></a>Popis pravidla
 Protože atributy jsou odvozeny z <xref:System.Attribute?displayProperty=fullName>a atributy se používají v době kompilace, jejich konstruktory mohou být předány pouze konstantní hodnoty. Parametry atributu, které musí představovat adresy URL, identifikátory GUID a verze nemůže být typu <xref:System.Uri?displayProperty=fullName>, <xref:System.Guid?displayProperty=fullName>, a <xref:System.Version?displayProperty=fullName>, protože tyto typy nemůže být reprezentovaná jako konstanty. Místo toho se musí být reprezentována řetězce.

 Protože parametr je zadán jako řetězec, je možné, že parametr nesprávně naformátovanou může předávat v době kompilace.

 Toto pravidlo používá pojmenování heuristiku k vyhledání parametrů, které představují identifikátor URI (URI), verze nebo globálně jedinečný identifikátor (GUID) a ověřuje, zda předaná hodnota je správný.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Změňte parametr řetězec správně vytvořená adresa URL, identifikátor GUID nebo verzi.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, je-li parametr nepředstavuje adresu URL, identifikátor GUID nebo verzi.

## <a name="example"></a>Příklad
 Následující příklad ukazuje kód pro AssemblyFileVersionAttribute, který porušuje tato pravidla.

 [!code-csharp[FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly/cs/FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly.cs#1)]

 Toto pravidlo aktivuje následující:

- Parametry, které obsahují 'version' a nejde ho parsovat na System.Version.

- Parametry, které obsahují 'guid' a nejde ho parsovat na System.Guid.

- Parametry, které obsahuje "uri", "urn" nebo "url" a nelze jej analyzovat na System.Uri.

## <a name="see-also"></a>Viz také
 [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

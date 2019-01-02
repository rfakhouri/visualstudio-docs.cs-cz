---
title: 'CA1719: Názvy parametrů by neměly odpovídat názvům členů'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ParameterNamesShouldNotMatchMemberNames
- CA1719
helpviewer_keywords:
- CA1719
- ParameterNamesShouldNotMatchMemberNames
ms.assetid: c6fea690-1659-4ee7-a1c5-125ad6754525
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0ca40c478eb383025755bff147dd9e0f47cecb79
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53868875"
---
# <a name="ca1719-parameter-names-should-not-match-member-names"></a>CA1719: Názvy parametrů by neměly odpovídat názvům členů

|||
|-|-|
|TypeName|ParameterNamesShouldNotMatchMemberNames|
|CheckId|CA1719|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název externě viditelného členu odpovídá v porovnávání, název jednoho ze svých parametrů.

## <a name="rule-description"></a>Popis pravidla
 Název parametru by měl sdělit význam parametru a název členu by měl sdělit význam členu. Byl by to vzácný návrh, pokud by byly stejné. Stejné pojmenování parametru i jeho členu je neintuitivní a činí knihovnu obtížně použitelnou.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Vyberte název parametru se neshoduje s názvem člena.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pro vývoj nových projektů, žádné známé scénáře nastat, pokud je třeba potlačit upozornění tohoto pravidla. Pro přesouvání knihovny, budete muset potlačit upozornění tohoto pravidla.

## <a name="related-rules"></a>Související pravidla
 [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708: Identifikátory by se měly lišit o více než velikostí písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

 [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
---
title: 'CA1722: Identifikátory by neměly mít nesprávnou předponu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotHaveIncorrectPrefix
- CA1722
helpviewer_keywords:
- CA1722
- IdentifiersShouldNotHaveIncorrectPrefix
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e997bce3c3e6cd96478e5b7ba6899d8563b4ac7e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55029671"
---
# <a name="ca1722-identifiers-should-not-have-incorrect-prefix"></a>CA1722: Identifikátory by neměly mít nesprávnou předponu

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectPrefix|
|CheckId|CA1722|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Identifikátor má nesprávnou předponu.

## <a name="rule-description"></a>Popis pravidla
 Podle konvence mají pouze některé programovací prvky názvy začínající určitou předponou.

 Názvy typů nemusí specifický prefix a by neměly mít předponu 'C'. Toto pravidlo oznámí porušení zásad pro názvy typů, jako je například "CMyClass" a nevytváří sestavu porušení zásad pro názvy typů, jako je například "Mezipaměti".

 Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. Taková konzistence snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odebrání předpony identifikátoru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="related-rules"></a>Související pravidla
 [CA1715: Identifikátory by měly mít správnou předponu](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)
---
title: 'CA1713: Události by neměly mít předponu před nebo po'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EventsShouldNotHaveBeforeOrAfterPrefix
- CA1713
helpviewer_keywords:
- CA1713
- EventsShouldNotHaveBeforeOrAfterPrefix
ms.assetid: 855772a4-aa9e-410b-88c1-c5fba1ca63da
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d8dba144740a2a39494323a456cddf90131e35c6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545880"
---
# <a name="ca1713-events-should-not-have-before-or-after-prefix"></a>CA1713: Události by neměly mít předponu před nebo po

|||
|-|-|
|TypeName|EventsShouldNotHaveBeforeOrAfterPrefix|
|CheckId|CA1713|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Název události začíná 'Before' a 'After'.

## <a name="rule-description"></a>Popis pravidla
 Názvy událostí, měl by popisovat akce, která vyvolává událost. Pro pojmenování souvisejících událostí vyvolaných v určitém pořadí je vhodné používat přítomný a minulý čas, který naznačí relativní pozici v pořadí akcí. Například při pojmenování dvojice událostí, který je vyvolána při zavření prostředek, můžete pojmenovat ho "Zavřít" a "Uzavřeno" místo "BeforeClose" a "AfterClose".

 Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odebrání předpony názvu události a zvažte možnost změnit název, který má používat přítomný a minulý čas slovesa.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.
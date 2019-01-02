---
title: 'CA2219: Nevyvolávejte výjimky v klauzulích výjimky'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4403ab65be60000bc758cf1a127e6b589c764702
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53857705"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219: Nevyvolávejte výjimky v klauzulích výjimky

|||
|-|-|
|TypeName|DoNotRaiseExceptionsInExceptionClauses|
|CheckId|CA2219|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné dopadem na dřívější kód|

## <a name="cause"></a>příčina
 Z je vyvolána výjimka `finally`, filtr nebo klauzule fault.

## <a name="rule-description"></a>Popis pravidla
 Když v klauzuli výjimka je vyvolána výjimka, výrazně zvyšuje obtížnost ladění.

 Když je výjimka vyvolána v `finally` nebo klauzule fault, nová výjimka skryje aktivní výjimku, pokud jsou k dispozici. To díky obtížné rozpoznání a ladění původní chyby.

 Pokud je v klauzuli filtru vyvolána výjimka, modul runtime bezobslužně zachytí výjimku a způsobí, že byl filtr vyhodnocen na hodnotu false. Neexistuje žádný způsob, jak zjistit rozdíl mezi vyhodnocení filtru na hodnotu false a výjimky se vyvolat z filtru. Tím je obtížné rozpoznat a ladit chyby v logice filtru.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li vyřešit porušení tohoto pravidla, nevyvolávejte explicitně výjimky z `finally`, filtr nebo klauzule fault.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla. Nejsou žádné scénáře, kdy výjimka vyvolána v klauzuli výjimek poskytuje výhoda pro provádění kódu.

## <a name="related-rules"></a>Související pravidla
 [CA1065: Nevyvolávejte výjimky v neočekávaných umístěních](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)

## <a name="see-also"></a>Viz také:
 [Upozornění ohledně návrhu](../code-quality/design-warnings.md)
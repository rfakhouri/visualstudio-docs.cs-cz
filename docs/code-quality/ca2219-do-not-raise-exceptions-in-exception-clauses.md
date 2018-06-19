---
title: 'CA2219: Nevyvolávejte výjimky v klauzulích výjimky'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
ms.openlocfilehash: 5d90e56eee9c68ff94b18204928ecaeeeb55ae0a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919531"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219: Nevyvolávejte výjimky v klauzulích výjimky
|||
|-|-|
|TypeName|DoNotRaiseExceptionsInExceptionClauses|
|CheckId|CA2219|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné dopadem na dřívější kód|

## <a name="cause"></a>příčina
 K výjimce `finally`, filtr nebo selhání klauzule.

## <a name="rule-description"></a>Popis pravidla
 Když dojde k výjimce v klauzuli výjimky, výrazně zvyšuje je obtížné ladění.

 Pokud je vyvolána výjimka v `finally` nebo selhání klauzule novou výjimku skryje active výjimka, pokud je k dispozici. Díky tomu původní chyba obtížné zjistit a ladění.

 Pokud v klauzuli filtru je vyvolána výjimka, modul runtime bezobslužně zachytí výjimky a způsobí, že filtr vyhodnotit na hodnotu false. Neexistuje žádný způsob, jak určit rozdíl mezi filtr vyhodnocení na hodnotu false a výjimku se výjimku z filtru. Díky tomu je obtížné zjistit a ladění chyby v jeho logiku.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li odstranit tento porušení toto pravidlo, není vyvolat explicitně výjimku z `finally`, filtr nebo selhání klauzule.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Není potlačení upozornění pro toto pravidlo. Neexistují žádné situací, za kterých výjimka vyvolána v klauzuli výjimka výhoda provádění kódu.

## <a name="related-rules"></a>Související pravidla
 [CA1065: Nevyvolávejte výjimky v neočekávaných umístěních](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)

## <a name="see-also"></a>Viz také
 [Upozornění ohledně návrhu](../code-quality/design-warnings.md)
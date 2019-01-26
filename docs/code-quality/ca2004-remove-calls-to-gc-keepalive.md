---
title: 'CA2004: Odeberte volání GC.KeepAlive'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e2787b3d0876034113e777d7f8932d63e5c1a27
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55001456"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: Odeberte volání GC.KeepAlive

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Použití třídy `SafeHandle` ale stále obsahovat volání `GC.KeepAlive`.

## <a name="rule-description"></a>Popis pravidla
 Pokud převádíte na `SafeHandle` využití, odeberte veškerá volání `GC.KeepAlive` (objekt). V tomto případě by neměl mít třídy volání `GC.KeepAlive`, za předpokladu, že nemají finalizační metodu, ale spoléhají na `SafeHandle` dokončete popisovač operačního systému pro ně.  I když náklady při volání k opuštění `GC.KeepAlive` může být nepatrné měřený podle výkonu, vnímání, který volání `GC.KeepAlive` je nezbytné nebo dostatečná k vyřešení problému, který již neexistuje provede kód obtížnější životnost Udržujte.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odeberte volání `GC.KeepAlive`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto upozornění můžete potlačit pouze v případě, že není technicky správné pro převod na `SafeHandle` využití ve své třídě.
---
title: 'CA2004: Odeberte volání uvolňování paměti. KeepAlive'
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0e025a8af3f7f5c1810abe2b9e182f607a29760e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53915827"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: Odeberte volání uvolňování paměti. KeepAlive

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Použití třídy `SafeHandle` ale stále obsahovat volání `GC.KeepAlive`.

## <a name="rule-description"></a>Popis pravidla
 Pokud převádíte na `SafeHandle` využití, odeberte veškerá volání `GC.KeepAlive` (objekt). V tomto případě by neměl mít třídy volání `GC.KeepAlive`, za předpokladu, že nemají finalizační metodu, ale spoléhají na `SafeHandle` dokončete popisovač operačního systému pro ně.  I když náklady při volání k opuštění `GC.KeepAlive` může být nepatrné měřený podle výkonu, vnímání, který volání `GC.KeepAlive` je nezbytné nebo dostatečná k vyřešení problému, který již neexistuje provede kód obtížnější životnost Udržujte.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odeberte volání `GC.KeepAlive`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto upozornění můžete potlačit pouze v případě, že není technicky správné pro převod na `SafeHandle` využití ve své třídě.
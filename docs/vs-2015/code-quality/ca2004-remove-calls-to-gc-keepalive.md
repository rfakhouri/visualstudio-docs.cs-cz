---
title: 'CA2004: Odeberte volání uvolňování paměti. KeepAlive | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3c8d35a94390e426fca47456046fb42820992668
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53961946"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: Odeberte volání uvolňování paměti. KeepAlive
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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

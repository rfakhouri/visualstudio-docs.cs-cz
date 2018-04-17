---
title: 'CA2004: Odeberte volání do globálního katalogu. KeepAlive | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: d25c42202f7df2214295af4e3d1a448266cfa6cb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: Odeberte volání GC.KeepAlive
|||  
|-|-|  
|TypeName|RemoveCallsToGCKeepAlive|  
|CheckId|CA2004|  
|Kategorie|Microsoft.Reliability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Použití třídy `SafeHandle` ale stále obsahovat volání `GC.KeepAlive`.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pokud převádíte na `SafeHandle` využití, odeberte všechna volání `GC.KeepAlive` (objekt). V takovém případě by neměl mít třídy volat `GC.KeepAlive`, za předpokladu, že nemají finalizační metody, ale závisí na `SafeHandle` k dokončení popisovač operačního systému pro ně.  I když náklady nechat v volání `GC.KeepAlive` může být nepatrné měřený podle výkonu, vnímání, volání `GC.KeepAlive` je nezbytné nebo dostatečná vyřešit problém, který již neexistuje díky kód obtížnější životnost Udržujte.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Odeberte volání `GC.KeepAlive`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Toto upozornění můžete potlačit pouze v případě, že není technicky správný převést `SafeHandle` využití v třídě.
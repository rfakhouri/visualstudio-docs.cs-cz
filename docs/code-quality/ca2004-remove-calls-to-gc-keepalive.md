---
title: "CA2004: Odeberte volání do globálního katalogu. KeepAlive | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dd6cc8b51ddd8f9e8813229cf66b9facb52e4668
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
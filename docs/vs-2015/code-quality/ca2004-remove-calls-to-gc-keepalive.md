---
title: 'CA2004: Odeberte volání uvolňování paměti. KeepAlive | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
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
ms.openlocfilehash: e14080db1a853d7ebfe0a8c5fe90bafffa624b17
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674702"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: Odeberte volání GC.KeepAlive
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2004: Odeberte volání uvolňování paměti. KeepAlive](https://docs.microsoft.com/visualstudio/code-quality/ca2004-remove-calls-to-gc-keepalive).  
  
TypeName | RemoveCallsToGCKeepAlive |  
| ID kontroly | CA2004 |  
| Kategorie | Microsoft.Reliability|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Použití třídy `SafeHandle` ale stále obsahovat volání `GC.KeepAlive`.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pokud převádíte na `SafeHandle` využití, odeberte veškerá volání `GC.KeepAlive` (objekt). V tomto případě by neměl mít třídy volání `GC.KeepAlive`, za předpokladu, že nemají finalizační metodu, ale spoléhají na `SafeHandle` dokončete popisovač operačního systému pro ně.  I když náklady při volání k opuštění `GC.KeepAlive` může být nepatrné měřený podle výkonu, vnímání, který volání `GC.KeepAlive` je nezbytné nebo dostatečná k vyřešení problému, který již neexistuje provede kód obtížnější životnost Udržujte.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Odeberte volání `GC.KeepAlive`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Toto upozornění můžete potlačit pouze v případě, že není technicky správné pro převod na `SafeHandle` využití ve své třídě.




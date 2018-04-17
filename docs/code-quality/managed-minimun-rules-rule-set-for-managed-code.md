---
title: Sada pravidel spravovaná minimální pravidla pro spravovaný kód | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 6c14af4c569749273b6ed6b73fe48249df3f1ee0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="managed-minimum-rules-rule-set-for-managed-code"></a>Pro spravovaný kód sada pravidel spravovaná minimální pravidla
Spravovaná minimální pravidla se zaměřit na nejdůležitější problémy ve vašem kódu, včetně potenciální bezpečnostní díry, dojde k chybě aplikace a další důležité chyby logiku a návrhu. Toto pravidlo nastavit v žádné sadě vlastní pravidlo, že které vytvoříte pro projekty by měla obsahovat.  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|Typy, které vlastní uvolnitelné pole by měly být uvolnitelné|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|Odstraňte prázdné finalizační metody|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Uvolnitelné pole by mělo být uvolněno|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|Přetižte operátor equals při přepsání ValueType.Equals|

---
title: Nastavení pravidel spravovaná minimální pravidla pro spravovaný kód | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: cca9670f65ef517a4697fc0752c65cbafbaa3b16
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667147"
---
# <a name="managed-minimun-rules-rule-set-for-managed-code"></a>Sada pravidel Spravovaná minimální pravidla pro spravovaný kód
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [sada pravidel spravovaná minimální pravidla pro spravovaný kód](https://docs.microsoft.com/visualstudio/code-quality/managed-minimun-rules-rule-set-for-managed-code).  
  
Spravovaná minimální pravidla se soustředí na nejdůležitější problémy v kódu, včetně možných bezpečnostních děr, selhání aplikace a jiných důležitých chyb logiky a návrhu. Měli byste zahrnout tuto sadu pravidel v jakékoli vlastní sadě pravidel, že kterou vytvoříte pro vaše projekty.  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|Typy, které vlastní uvolnitelné pole by měly být uvolnitelné|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|Odstraňte prázdné finalizační metody|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Uvolnitelné pole by mělo být uvolněno|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|Přetižte operátor equals při přepsání ValueType.Equals|




---
title: 'DA0006: Přepište Equals() pro typy hodnot | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAOverrideEquals
- vs.performance.6
- vs.performance.DA0006
- vs.performance.rules.DA0006
ms.assetid: 4d85bdd6-b571-47e0-afd6-ba3764e4eed5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b360c97e64842d46fe2b121e8505ac0f9cafebed
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="da0006-override-equals-for-value-types"></a>DA0006: Přepište Equals() pro hodnoty
|||  
|-|-|  
|Id pravidla|DA0006|  
|Kategorie|Použití rozhraní .NET framework|  
|Profiiling metody|Vzorkování|  
|Zpráva|Přepište rovná se a operátor rovnosti u typů hodnot.|  
|Typ Messge|Upozornění|  
  
## <a name="cause"></a>příčina  
 Volání metody Equals nebo operátory rovnosti typu veřejné hodnoty jsou podstatnou část data profilování. Zvažte implementaci efektivnější metoda.  
  
## <a name="rule-description"></a>Popis pravidla  
 U typů hodnot, zděděné implementace rovná se používá <xref:System.Reflection> knihovny a porovná obsah všech polí v typu. Reflexe je výpočetně náročná a porovnání rovnosti všech polí může být zbytečné. Pokud budou uživatelé k porovnání nebo řazení instance nebo používat jako hash klíče tabulky, váš typ hodnoty by měla implementovat rovná se. Pokud si programovací jazyk podporuje přetížení operátoru, měli byste také poskytnout implementaci operátory rovnosti a nerovnosti.  
  
 Další informace o tom, jak přepsání Equals a operátory rovnosti najdete v tématu [pokyny pro implementaci rovná se a operátor rovnosti (==)](http://go.microsoft.com/fwlink/?LinkId=177818).  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Příklad implementace rovná a operátory rovnosti, naleznete v části pravidel nástroje Analýza kódu [CA1815: přepište rovná se a operátor rovnosti na hodnotových typech](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)
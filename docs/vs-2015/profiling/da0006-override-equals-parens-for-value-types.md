---
title: 'DA0006: Přepište Equals() pro hodnoty | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DAOverrideEquals
- vs.performance.6
- vs.performance.DA0006
- vs.performance.rules.DA0006
ms.assetid: 4d85bdd6-b571-47e0-afd6-ba3764e4eed5
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2229edad7ff338251fea23740343e23f87aa2792
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68158670"
---
# <a name="da0006-override-equals-for-value-types"></a>DA0006: Přepis Equals() pro typy hodnot
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id pravidla | DA0006 |  
| Kategorie |. Použití rozhraní .NET Framework |  
| Metody Profiiling | Vzorkování |  
| Zpráva | Přepište Equals a operátory rovnosti na hodnotových typech. |  
| Typ Messge | Upozornění |  
  
## <a name="cause"></a>příčina  
 Volání metody Equals a operátory rovnosti veřejné hodnotového typu je podstatnou část dat profilování. Zvažte implementaci metodu efektivnější.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pro hodnotové typy používá zděděná implementace metody Equals <xref:System.Reflection> knihovny a porovnává obsah všech polí v typu. Reflexe je výpočetně náročná a porovnání rovnosti všech polí může být zbytečné. Pokud očekáváte, že uživatelé budou porovnávat nebo třídit instance nebo používat jako klíče zatřiďovací tabulky, by měl typ hodnoty implementovat metodu Equals. Pokud svůj oblíbený programovací jazyk podporuje přetížení operátoru, měli byste také poskytnout implementaci pro operátory rovnosti a nerovnosti.  
  
 Další informace o tom, jak přepsat Equals a operátory rovnosti, naleznete v tématu [pokyny pro implementaci rovná se a operátor rovnosti (==)](http://go.microsoft.com/fwlink/?LinkId=177818).  
  
## <a name="how-to-investigate-a-warning"></a>Zkoumání upozornění  
 Příklad implementace Equals a operátory rovnosti, naleznete v tématu pravidel nástroje Analýza kódu [CA1815: Přepište rovná se a operátor rovnosti na hodnotových typech](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)

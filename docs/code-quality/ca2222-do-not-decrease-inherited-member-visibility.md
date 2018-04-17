---
title: 'CA2222: Nesnižujte viditelnost zděděného členu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
helpviewer_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
ms.assetid: 066c8675-381f-43cc-956c-d757cc494028
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de96b199adf5b282f70207478e4d9ae38c4d00f5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2222-do-not-decrease-inherited-member-visibility"></a>CA2222: Nesnižujte viditelnost zděděného členu
|||  
|-|-|  
|TypeName|DoNotDecreaseInheritedMemberVisibility|  
|CheckId|CA2222|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Soukromá metoda nezapečetěných typ má podpisu, který je stejný jako veřejná metoda deklarované v základním typu. Soukromá metoda není vyčerpávající.  
  
## <a name="rule-description"></a>Popis pravidla  
 Modifikátor přístupu byste neměli měnit u zděděných členů. Změna zděděného členu na soukromý nezabrání volajícím v přístupu k implementaci základní třídy dané metody. Pokud člen přišla privátní a typ nezapečetěná, dědění typy můžete volat poslední veřejné implementace metody v hierarchii dědičnosti. Pokud potřebujete změnit – modifikátor přístupu, metoda by měl být označen konečné nebo jeho typ by měl být zapečetěný aby metodu přepsání.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, změňte přístup k být veřejné. Případně pokud si programovací jazyk podporuje, můžete nastavit metodu poslední.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který je v rozporu toto pravidlo.  
  
 [!code-vb[FxCop.Usage.InheritedPublic#1](../code-quality/codesnippet/VisualBasic/ca2222-do-not-decrease-inherited-member-visibility_1.vb)]
 [!code-csharp[FxCop.Usage.InheritedPublic#1](../code-quality/codesnippet/CSharp/ca2222-do-not-decrease-inherited-member-visibility_1.cs)]
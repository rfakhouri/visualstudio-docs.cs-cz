---
title: 'CA2226: Operátory by měly mít symetrické přetížení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
helpviewer_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
ms.assetid: d202401a-ea14-4559-b15e-0ea4f5b68789
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 17ce9653f5763788b8a6988994c379fc885152ad
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2226-operators-should-have-symmetrical-overloads"></a>CA2226: Operátory by měly mít symetrické přetížení
|||  
|-|-|  
|TypeName|OperatorsShouldHaveSymmetricalOverloads|  
|CheckId|CA2226|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Typ implementuje operátor rovnosti nebo nerovnosti a neimplementuje opačný operátor.  
  
## <a name="rule-description"></a>Popis pravidla  
 Neexistují žádné okolností, kde rovnosti nebo nerovnosti se vztahuje k instancím typu a opačně orientované operátor není definován. Operátor nerovnosti typy obvykle implementovat vrácením posunut hodnotu operátor rovnosti.  
  
 Kompilátor jazyka C# vydává chybu pro porušení toto pravidlo.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, implementují rovnosti a operátory nerovnosti nebo odebrat ten, který je k dispozici.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Typ vašeho nebude fungovat způsobem, který je v souladu s [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1046: Nepřetěžujte operátory rovnosti na odkazových typech](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: Přetížení operátoru mají pojmenované alternativy](../code-quality/ca2225-operator-overloads-have-named-alternates.md)  
  
 [CA2224: Přepište Equals při přetížení operátoru rovnosti](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2218: Přepište GetHashCode při přepsání Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)  
  
 [CA2231: Přetižte operátor equals při přepsání ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)
---
title: 'CA2146: Typy musí být alespoň tak kritické, jako jejich základní typy a rozhraní | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2146
ms.assetid: 241fb784-1f6b-46e5-8ceb-c438e341d38e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b956397818c171091e4ad982d92adc5e62370a39
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces"></a>CA2146: Typy nesmějí být kritické méně než jejich základní typy a rozhraní
|||  
|-|-|  
|TypeName|TypesMustBeAtLeastAsCriticalAsBaseTypes|  
|CheckId|CA2146|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Transparentní typ je odvozen od typu, který je označený s <xref:System.Security.SecuritySafeCriticalAttribute> nebo <xref:System.Security.SecurityCriticalAttribute>, nebo typu, který je označený s <xref:System.Security.SecuritySafeCriticalAttribute> atribut je odvozený od typu, který je označené <xref:System.Security.SecurityCriticalAttribute> atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo je vyvoláno, když má odvozený typ atribut transparentnosti zabezpečení, který není tak kritický jako jeho základní typ nebo implementované rozhraní. Pouze kritické typy lze odvodit z kritických základních typů nebo mohou implementovat kritická rozhraní a pouze kritické typy nebo bezpečně kritické typy mohou být odvozeny ze základních bezpečně kritických typů nebo mohou implementovat bezpečně kritická rozhraní. Výsledkem porušení toto pravidlo v průhlednost úrovně 2 <xref:System.TypeLoadException> pro odvozený typ.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li odstranit tento porušení, označte odvozené nebo prováděcí typ s průhlednost atribut, který je důležité jako základní typ nebo rozhraní.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../code-quality/codesnippet/CSharp/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces_1.cs)]
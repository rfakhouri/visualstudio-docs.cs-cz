---
title: "CA2136: Členy nesmějí mít konfliktní poznámky transparentnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: aad39e8b42a709aabc6321718a671510a5b686da
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: Členy nesmějí mít konfliktní poznámky transparentnosti
|||  
|-|-|  
|TypeName|TransparencyAnnotationsShouldNotConflict|  
|CheckId|CA2136|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Toto pravidlo aktivuje se v případě, že je označené jako člena typu <xref:System.Security> zabezpečení atributu, který má jinou průhlednost než hodnota atributu zabezpečení kontejneru člena.  
  
## <a name="rule-description"></a>Popis pravidla  
 Atributy transparentnosti jsou použity z prvků kódu většího rozsahu na prvky menšího rozsahu. Atributy transparentnosti prvků kódu, které mají větší rozsah, mají přednost před atributy transparentnosti prvků kódu, které jsou obsaženy v prvním prvku. Například třídu, která je označena <xref:System.Security.SecurityCriticalAttribute> atributu nesmí obsahovat metodu, která je označena <xref:System.Security.SecuritySafeCriticalAttribute> atribut.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li odstranit tento porušení, odeberte atribut zabezpečení z elementu kód, který má nižší rozsah nebo změnit jeho atribut, aby byla stejná jako obsahující element kódu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Není potlačení upozornění od tohoto pravidla.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu je označené metodu <xref:System.Security.SecuritySafeCriticalAttribute> atribut a je členem skupiny třídu, která je označena <xref:System.Security.SecurityCriticalAttribute> atribut. Atribut bezpečné zabezpečení byste měli odebrat.  
  
 [!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../code-quality/codesnippet/CSharp/ca2136-members-should-not-have-conflicting-transparency-annotations_1.cs)]
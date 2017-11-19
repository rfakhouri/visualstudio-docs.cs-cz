---
title: "CA2214: Nevolejte přepisovatelné metody v konstruktorech | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bbe640ac82c159b39721ddac27b9d65926c60647
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2214-do-not-call-overridable-methods-in-constructors"></a>CA2214: Nevolejte přepisovatelné metody v konstruktorech
|||  
|-|-|  
|TypeName|DoNotCallOverridableMethodsInConstructors|  
|CheckId|CA2214|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Konstruktor typu nezapečetěných volá metodu virtuální definovaný ve své třídě.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pokud virtuální metoda je volána, skutečný typ, který provede metodu nevyberete až při spuštění. Když Konstruktor volá virtuální metodu, je možné, že nebyl proveden v konstruktoru pro instanci, která volá metodu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, nevolejte virtuální metody typu z konstruktorů typu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Omezit volání virtuální metody by se měla změnit konstruktoru.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje účinek bychom při tom porušili toto pravidlo. Testovací aplikace vytvoří instanci `DerivedType`, což způsobí, že její základní třída (`BadlyConstructedType`) konstruktor provést. `BadlyConstructedType`pro konstruktor nesprávně volá metodu virtuální `DoSomething`. Jak ukazuje výstup `DerivedType.DoSomething()` provede a nebude proto před `DerivedType`na konstruktoru.  
  
 [!code-csharp[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/CSharp/ca2214-do-not-call-overridable-methods-in-constructors_1.cs)]
 [!code-vb[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/VisualBasic/ca2214-do-not-call-overridable-methods-in-constructors_1.vb)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **Volání metody základní konstruktoru.**  
**Je volána odvozené DoSomething - inicializovat? Ne**  
**Odvozené volání konstruktoru.**
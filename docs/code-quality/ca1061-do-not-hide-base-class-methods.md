---
title: "CA1061: Neskrývejte metody třídy base | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d7eb4db46697e7f4cbb54d9ee11e4289b5a2ba2c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: Neskrývejte metody třídy base
|||  
|-|-|  
|TypeName|DoNotHideBaseClassMethods|  
|CheckId|CA1061|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Odvozený typ deklaruje metodu se stejným názvem a stejný počet parametrů jako jedna z jeho základní metody; jeden nebo více parametrů je základní typ odpovídající parametr v metodě základní; a všechny ostatní parametry mají typy, které jsou stejné jako odpovídající parametry v základní metody.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metoda v základním typu skrytý stejně jako s názvem metodou v odvozeném typu, pokud parametr podpis odvozené metoda se liší pouze podle typů, které jsou více slabě odvozené než odpovídající typy v parametru podpis základní metody.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, odebrat nebo přejmenovat metodu nebo změňte parametr podpis tak, aby metoda není skrýt základní metody.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, která porušuje pravidlo.  
  
 [!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]
---
title: "CA1012: Abstraktní typy by neměly mít konstruktory | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AbstractTypesShouldNotHaveConstructors
- CA1012
helpviewer_keywords: CA1012
ms.assetid: 09f458ac-dd88-4cd7-a47f-4106c1e80ece
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 394621874110ccae04837a991e66e2773700c33f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1012-abstract-types-should-not-have-constructors"></a>CA1012: Abstraktní typy by neměly mít konstruktory
|||  
|-|-|  
|TypeName|AbstractTypesShouldNotHaveConstructors|  
|CheckId|CA1012|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Veřejného typu je abstraktní a nemá veřejný konstruktor.  
  
## <a name="rule-description"></a>Popis pravidla  
 Konstruktory abstraktních typů mohou být volány pouze odvozenými typy. Jelikož veřejné konstruktory vytvářejí instance typu, přičemž nelze vytvořit instance abstraktního typu, je abstraktní typ obsahující veřejný konstruktor nesprávně navržen.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, zkontrolujte konstruktor chráněný nebo nedeklarujte typ jako abstraktní.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Abstraktní typ je veřejný konstruktor.  
  
## <a name="example"></a>Příklad  
 Následující příklad obsahuje abstraktní typ, který je v rozporu toto pravidlo.  
  
 [!code-vb[FxCop.Design.AbstractTypeBad#1](../code-quality/codesnippet/VisualBasic/ca1012-abstract-types-should-not-have-constructors_1.vb)]
 [!code-csharp[FxCop.Design.AbstractTypeBad#1](../code-quality/codesnippet/CSharp/ca1012-abstract-types-should-not-have-constructors_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující příklad opravy předchozí porušení změnou usnadnění konstruktoru z `public` k `protected`.  
  
 [!code-csharp[FxCop.Design.AbstractTypeGood#1](../code-quality/codesnippet/CSharp/ca1012-abstract-types-should-not-have-constructors_2.cs)]
 [!code-vb[FxCop.Design.AbstractTypeGood#1](../code-quality/codesnippet/VisualBasic/ca1012-abstract-types-should-not-have-constructors_2.vb)]
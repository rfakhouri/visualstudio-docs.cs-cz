---
title: "CA1053: Statický vlastník typů by neměly mít konstruktory | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a9e9d6272fbb21644daab96bb3ccd7d02b023840
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1053-static-holder-types-should-not-have-constructors"></a>CA1053: Statický vlastník typů by neměl mít konstruktory
|||  
|-|-|  
|TypeName|StaticHolderTypesShouldNotHaveConstructors|  
|CheckId|CA1053|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Veřejný nebo vnořený veřejný typ deklaruje pouze statické členy a má veřejný nebo chráněný výchozí konstruktor.  
  
## <a name="rule-description"></a>Popis pravidla  
 Konstruktor není nutný, protože volání statických členů nevyžaduje instanci typu. Navíc vzhledem k tomu, že typ nemá nestatické členy, vytvoření instance neposkytuje přístup k jakémukoli typu členů.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, odeberte výchozí konstruktor nebo nastavit jako soukromé.  
  
> [!NOTE]
>  Některé kompilátory automaticky vytvoří výchozí veřejný konstruktor, pokud typ nedefinuje žádné konstruktory. Pokud je tomu u vašeho typu, přidejte privátní výchozí konstruktor eliminovat porušení zásady.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Přítomnost konstruktoru naznačuje, že typ není typu statické.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který je v rozporu toto pravidlo. Všimněte si, že neexistuje žádný výchozí konstruktor ve zdrojovém kódu. Když tento kód se zkompiluje do sestavení, kompilátor jazyka C# vloží výchozí konstruktor, který bude toto pravidlo porušují. Chcete-li vyřešit tento problém, deklarujte soukromý konstruktor.  
  
 [!code-csharp[FxCop.Design.StaticTypes#1](../code-quality/codesnippet/CSharp/ca1053-static-holder-types-should-not-have-constructors_1.cs)]
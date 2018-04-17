---
title: 'CA1814: Preferujte Vícenásobná pole více než multidimenzionální | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
helpviewer_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
ms.assetid: b1ccf563-2ec8-42e5-b89c-731a9de1ea1d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2f87c0141b437cebce2531b5b1ec4cd983fa1822
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1814-prefer-jagged-arrays-over-multidimensional"></a>CA1814: Preferujte vícenásobná pole více než multidimenzionální
|||  
|-|-|  
|TypeName|PreferJaggedArraysOverMultidimensional|  
|CheckId|CA1814|  
|Kategorie|Microsoft.Performance|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Člen je deklarován jako multidimenzionálního pole.  
  
## <a name="rule-description"></a>Popis pravidla  
 Vícenásobné pole je pole, jehož prvky jsou pole. Pole tvořící prvky mohou být různě velká, což vede k menšímu nevyužitému místu u některých sad dat.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, změňte multidimenzionálního pole na Vícenásobná pole.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo, je-li multidimenzionálního pole. nezpracovává zbytečně místa.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje deklarace pro vícenásobná a multidimenzionální pole.  
  
 [!code-vb[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/VisualBasic/ca1814-prefer-jagged-arrays-over-multidimensional_1.vb)]
 [!code-csharp[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/CSharp/ca1814-prefer-jagged-arrays-over-multidimensional_1.cs)]
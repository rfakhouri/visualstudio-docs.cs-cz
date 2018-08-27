---
title: 'CA1814: Preferujte Vícenásobná pole více než multidimenzionální | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
helpviewer_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
ms.assetid: b1ccf563-2ec8-42e5-b89c-731a9de1ea1d
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 290e2f736e347aef68296207048f8ba5787234cc
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900289"
---
# <a name="ca1814-prefer-jagged-arrays-over-multidimensional"></a>CA1814: Preferujte vícenásobná pole více než multidimenzionální
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1814: raději Vícenásobná pole více než multidimenzionální](https://docs.microsoft.com/visualstudio/code-quality/ca1814-prefer-jagged-arrays-over-multidimensional).

|||
|-|-|
|TypeName|PreferJaggedArraysOverMultidimensional|
|CheckId|CA1814|
|Kategorie|Microsoft.Performance|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Člen je deklarovaný jako multidimenzionálního pole.

## <a name="rule-description"></a>Popis pravidla
 Vícenásobné pole je pole, jehož prvky jsou pole. Pole tvořící prvky mohou být různě velká, což vede k menšímu nevyužitému místu u některých sad dat.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte vícerozměrné pole na vícenásobného pole.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, je-li multidimenzionální pole nejsou plýtvat vaším místa.

## <a name="example"></a>Příklad
 Následující příklad ukazuje deklarace pro vícenásobné a vícedimenzionální pole.

 [!code-csharp[FxCop.Performance.JaggedArrays#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.JaggedArrays/cs/FxCop.Performance.JaggedArrays.cs#1)]
 [!code-vb[FxCop.Performance.JaggedArrays#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.JaggedArrays/vb/FxCop.Performance.JaggedArrays.vb#1)]




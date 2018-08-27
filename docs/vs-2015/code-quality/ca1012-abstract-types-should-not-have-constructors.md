---
title: 'CA1012: Abstraktní typy by neměly mít konstruktory | Dokumentace Microsoftu'
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
- AbstractTypesShouldNotHaveConstructors
- CA1012
helpviewer_keywords:
- CA1012
ms.assetid: 09f458ac-dd88-4cd7-a47f-4106c1e80ece
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 692dfc0ad69cf4d71d82953e2cc9965733915dc6
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42901794"
---
# <a name="ca1012-abstract-types-should-not-have-constructors"></a>CA1012: Abstraktní typy by neměly mít konstruktory
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1012: abstraktní typy by neměly mít konstruktory](https://docs.microsoft.com/visualstudio/code-quality/ca1012-abstract-types-should-not-have-constructors).

|||
|-|-|
|TypeName|AbstractTypesShouldNotHaveConstructors|
|CheckId|CA1012|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Veřejný typ je abstraktní a nemá veřejný konstruktor.

## <a name="rule-description"></a>Popis pravidla
 Konstruktory abstraktních typů mohou být volány pouze odvozenými typy. Jelikož veřejné konstruktory vytvářejí instance typu, přičemž nelze vytvořit instance abstraktního typu, je abstraktní typ obsahující veřejný konstruktor nesprávně navržen.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zajistit konstruktoru chráněný, nebo nedeklarujte typ jako abstraktní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Abstraktní typ nemá veřejný konstruktor.

## <a name="example"></a>Příklad
 Následující příklad obsahuje abstraktní typ, který porušuje tato pravidla.

 [!code-csharp[FxCop.Design.AbstractTypeBad#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AbstractTypeBad/cs/FxCop.Design.AbstractTypeBad.cs#1)]
 [!code-vb[FxCop.Design.AbstractTypeBad#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AbstractTypeBad/vb/FxCop.Design.AbstractTypeBad.vb#1)]

## <a name="example"></a>Příklad
 Následující příklad opravuje předchozí porušení změnou usnadnění konstruktoru z `public` k `protected`.

 [!code-csharp[FxCop.Design.AbstractTypeGood#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AbstractTypeGood/cs/FxCop.Design.AbstractTypeGood.cs#1)]
 [!code-vb[FxCop.Design.AbstractTypeGood#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AbstractTypeGood/vb/FxCop.Design.AbstractTypeGood.vb#1)]




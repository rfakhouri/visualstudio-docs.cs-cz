---
title: 'CA1061: Neskrývejte metody základní třídy | Dokumentace Microsoftu'
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
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f018abbb864533e5c9d7b598638a4006a69ab2f3
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900339"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: Neskrývejte metody třídy base
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1061: neskrývejte metody třídy base](https://docs.microsoft.com/visualstudio/code-quality/ca1061-do-not-hide-base-class-methods).

|||
|-|-|
|TypeName|DoNotHideBaseClassMethods|
|CheckId|CA1061|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Odvozený typ deklaruje metodu se stejným názvem a číslem stejné parametry jako jeden z jeho základních metod; jeden nebo více parametrů je základní typ odpovídající parametr v základní metoda; a všechny zbývající parametry mají typy, které jsou stejné pro odpovídající parametry v základní metodě.

## <a name="rule-description"></a>Popis pravidla
 Metodu v základním typu je skryta identicky pojmenovanou metodou v odvozeném typu při předpis parametrů odvozené metody se liší jenom podle typů, které jsou více slabě odvozený než odpovídající typy v podpisu parametr základní metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odebrat nebo přejmenovat metodu nebo změnit předpis parametrů, takže metoda neskryje základní metoda.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která porušuje pravidlo.

 [!code-csharp[FxCop.Design.HideBaseMethod#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.HideBaseMethod/cs/FxCop.Design.HideBaseMethod.cs#1)]




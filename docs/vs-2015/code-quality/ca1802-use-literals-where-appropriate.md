---
title: 'CA1802: Použijte literály, kde je to vhodné | Dokumentace Microsoftu'
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
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 11617cc09ef822ce518b118ff5685f0b1a313feb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667744"
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802: Použijte literály, kde je to vhodné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1802: použijte literály kde odpovídající](https://docs.microsoft.com/visualstudio/code-quality/ca1802-use-literals-where-appropriate).  
  
TypeName | UseLiteralsWhereAppropriate |  
| ID kontroly | CA1802 |  
| Kategorie | Microsoft.Performance|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Pole je deklarován `static` a `readonly` (`Shared` a `ReadOnly` v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) a je inicializován s hodnotou, kterou lze vypočítat v době kompilace.  
  
## <a name="rule-description"></a>Popis pravidla  
 Hodnota `static``readonly` pole je vypočítán za běhu při volání statického konstruktoru pro deklarujícího typu. Pokud `static``readonly` pole je inicializováno při deklaraci a statický konstruktor není explicitně deklarované, kompilátor vydává statický konstruktor k inicializaci pole.  
  
 Hodnota `const` pole je vypočítána v době kompilace a uložená v metadatech, což zvyšuje výkon modulu runtime srovnání s `static``readonly` pole.  
  
 Protože hodnotu přiřazenou cílovému poli je nelze vypočítat v době kompilace, změňte deklaraci do `const` pole tak, aby hodnota byla vypočítána v době kompilace místo za běhu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, nahraďte `static` a `readonly` modifikátory `const` modifikátor.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění tohoto pravidla nebo zakázat pravidlo, pokud výkon není žádný problém.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, `UseReadOnly`, který porušuje pravidla a typ, `UseConstant`, vyhovující pravidlo.  
  
 [!code-csharp[FxCop.Performance.UseLiterals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UseLiterals/cs/FxCop.Performance.UseLiterals.cs#1)]
 [!code-vb[FxCop.Performance.UseLiterals#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.UseLiterals/vb/FxCop.Performance.UseLiterals.vb#1)]




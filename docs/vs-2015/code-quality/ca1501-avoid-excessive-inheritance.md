---
title: 'CA1501: Vyhněte se nadměrné dědičnosti | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1501
- AvoidExcessiveInheritance
helpviewer_keywords:
- AvoidExcessiveInheritance
- CA1501
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 420e9492fc5ab431710d62e1d8ea3c1bd8a31ce9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68191483"
---
# <a name="ca1501-avoid-excessive-inheritance"></a>CA1501: Vyhněte se nadměrné dědičnosti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidExcessiveInheritance|
|CheckId|CA1501|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ je více než čtyři úrovně hluboko v hierarchii dědičnosti.

## <a name="rule-description"></a>Popis pravidla
 Hluboce vnořené hierarchie typů může být obtížné sledovat, pochopit a udržovat. Toto pravidlo omezuje na hierarchie ve stejném modulu analýzy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odvození typu od základního typu, který je míň podrobné v hierarchii dědičnosti nebo odstranit některé zprostředkující základních typů.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla. Kód může být obtížné udržovat. Všimněte si, že v závislosti na tom, zda se základní typy, řešení porušení tohoto pravidla může vytvořit nejnovější změny. Například odebrání veřejných základních typů je zásadní změnu.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla.

 [!code-csharp[FxCop.Maintainability.ExcessiveInheritance#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Maintainability.ExcessiveInheritance/cs/FxCop.Maintainability.ExcessiveInheritance.cs#1)]
 [!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Maintainability.ExcessiveInheritance/vb/FxCop.Maintainability.ExcessiveInheritance.vb#1)]

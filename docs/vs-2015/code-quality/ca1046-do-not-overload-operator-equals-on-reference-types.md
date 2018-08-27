---
title: 'CA1046: Nepřetěžujte operátory rovnosti na odkazových typech | Dokumentace Microsoftu'
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
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1f4f37f6d4c2662ca0b053e6737c57ba222b0b5e
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900954"
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046: Nepřetěžujte operátory rovnosti na odkazových typech
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1046: Nepřetěžujte operátory rovnosti na odkazových typech](https://docs.microsoft.com/visualstudio/code-quality/ca1046-do-not-overload-operator-equals-on-reference-types).

|||
|-|-|
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|
|CheckId|CA1046|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Odkaz na veřejný nebo vnořený veřejný typ přetížení operátoru rovnosti.

## <a name="rule-description"></a>Popis pravidla
 U referenčních typů je výchozí implementace operátoru rovnosti téměř vždy správná. Ve výchozím nastavení jsou dva odkazy rovny, pouze pokud ukazují na stejný objekt.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte implementace operátoru rovnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud typ odkazu se chová jako předdefinovaného hodnotového typu. Pokud je smysluplná provedete sčítání a odčítání na instance daného typu, je nejspíš správná implementace operátoru rovnosti a potlačit porušení zásady.

## <a name="example"></a>Příklad
 Následující příklad ukazuje výchozí chování při porovnávání dva odkazy.

 [!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.RefTypesNoEqualityOp/cs/FxCop.Design.RefTypesNoEqualityOp.cs#1)]

## <a name="example"></a>Příklad
 Následující aplikace porovnává některé odkazy.

 [!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestRefTypesNoEqualityOp/cs/FxCop.Design.TestRefTypesNoEqualityOp.cs#1)]

 Tento příklad vytvoří následující výstup.

 **= nové (2,2) a b = nové (2,2) jsou stejné? Ne**
**c a a jsou stejné? Ano**
**b a a jsou ==? Ne**
**c a a jsou ==? Ano**
## <a name="related-rules"></a>Související pravidla
 [CA1013: Přetižte operátor rovnosti společně s přetížením operátorů sčítání a odečítání](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)

## <a name="see-also"></a>Viz také
 <xref:System.Object.Equals%2A?displayProperty=fullName> [Operátory rovnosti](http://msdn.microsoft.com/library/bc496a91-fefb-4ce0-ab4c-61f09964119a)




---
title: 'CA1046: Nepřetěžujte operátory rovnosti na odkazových typech | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
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
ms.openlocfilehash: b5543b2d968e96cbd5bf8c9f6dd015b2acf31b4c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62536048"
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046: Nepřetěžujte operátory rovnosti u odkazových typů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|
|CheckId|CA1046|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
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
 [CA1013: Přetižte operátor rovnosti při přetížení operátorů sčítání a odečítání](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)

## <a name="see-also"></a>Viz také
 <xref:System.Object.Equals%2A?displayProperty=fullName> [Operátory rovnosti](http://msdn.microsoft.com/library/bc496a91-fefb-4ce0-ab4c-61f09964119a)

---
title: 'CA2137: Transparentní metody musejí obsahovat pouze ověřitelné IL | Dokumentace Microsoftu'
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
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 77ff02a0db733c3151f4faccd00e07518d61e600
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900303"
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137: Transparentní metody musejí obsahovat pouze ověřitelné IL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2137: transparentní metody musejí obsahovat pouze ověřitelné IL](https://docs.microsoft.com/visualstudio/code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il).

|||
|-|-|
|TypeName|TransparentMethodsMustBeVerifiable|
|CheckId|CA2137|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Metoda obsahuje kód, který nelze ověřit, nebo vrací typ odkazem.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno při pokusech transparentního kódu zabezpečení spustit jazyk MSIL (Microsoft Intermediate Language), který nelze ověřit. Pravidlo však neobsahuje úplný ověřovatel jazyka IL a místo toho k zachycení většiny porušení ověření jazyka MSIL používá heuristiky.

 Ujistěte se, že váš kód obsahuje pouze ověřitelného kódu MSIL, spusťte [Peverify.exe (Nástroj PEVerify)](http://msdn.microsoft.com/library/f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa) v sestavení. Spustit PEVerify s **/ transparentní** možnost, která omezí výstup na pouze neověřitelný transparentních metodách, které by způsobilo chybu. Pokud / není použita možnost transparentní, PEVerify také ověří kritické metody, které můžou obsahovat kód, který nelze ověřit.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, označte metody <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut, nebo odeberte neověřitelný kód.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Metoda v tomto příkladu používá neověřitelný kód a by měly být označené <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.

 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2137.transparentmethodsmustbeverifiable/cs/ca2137 - transparentmethodsmustbeverifiable.cs#1)]




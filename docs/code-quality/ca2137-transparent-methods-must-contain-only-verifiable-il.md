---
title: "CA2137: Transparentní metody musejí obsahovat pouze ověřitelné IL | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3ec0dda4db164f4bd3368f1bb90c782f4aee6024
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137: Transparentní metody musejí obsahovat pouze ověřitelné IL
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
  
 Ujistěte se, že kód obsahuje pouze ověřitelné MSIL, spusťte [Peverify.exe (Nástroj PEVerify)](/dotnet/framework/tools/peverify-exe-peverify-tool) na vaše sestavení. Spustit PEVerify s **/ transparentní** možnost, která omezí výstup pouze neověřitelný transparentní metody, které by způsobilo chybu. Pokud / není transparentní možnost použít, PEVerify také ověří nejdůležitější metody, které můžou obsahovat kód, který nelze ověřit.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, označit metodu s <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut, nebo odeberte neověřitelný kód.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Metoda v tomto příkladu používá neověřitelný kód a musí být označen <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.  
  
 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../code-quality/codesnippet/CSharp/ca2137-transparent-methods-must-contain-only-verifiable-il_1.cs)]
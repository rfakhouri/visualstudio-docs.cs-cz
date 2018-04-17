---
title: 'CA2139: Transparentní metody nemusejí podporovat použití atributu HandleProcessCorruptingExceptions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2139
ms.assetid: 45a0328a-add7-40f9-8934-dff59beb02b3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a77100ce43480c797b15d28699923e4370a22c48
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute"></a>CA2139: Transparentní metody nemusejí podporovat použití atributu HandleProcessCorruptingExceptions
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotHandleProcessCorruptingExceptions|  
|CheckId|CA2139|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Transparentní metoda je označena <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo aktivuje jakákoli metoda, která je transparentní a pokusí se zpracování procesu poškozování výjimky pomocí <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut. Proces poškozování výjimka je klasifikace výjimky CLR verze 4.0 výjimek takové <xref:System.AccessViolationException>. Atribut HandleProcessCorruptedStateExceptionsAttribute lze použít pouze metodami kritickými pro bezpečnost a bude ignorován, je-li použit u transparentních metod. Zpracování výjimek poskozeny proces, musí se tato metoda stát kritické pro zabezpečení nebo bezpečné kritické pro zabezpečení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut, nebo označit metodu s <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu je označené transparentní metody <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut a se nezdaří pravidlo. Metoda by měl být označen také s <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.  
  
 [!code-csharp[FxCop.Security.CA2139.TransparentMethodsMustNotHandleProcessCorruptingExceptions#1](../code-quality/codesnippet/CSharp/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute_1.cs)]
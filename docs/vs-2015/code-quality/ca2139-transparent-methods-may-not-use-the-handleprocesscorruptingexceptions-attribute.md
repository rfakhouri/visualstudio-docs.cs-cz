---
title: 'CA2139: Transparentní metody nemusejí podporovat použití atributu HandleProcessCorruptingExceptions | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2139
ms.assetid: 45a0328a-add7-40f9-8934-dff59beb02b3
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a05813d01a05c02455d43e74029251e96e4e4580
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54765894"
---
# <a name="ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute"></a>CA2139: Transparentní metody nemusí používat atribut HandleProcessCorruptingExceptions
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsMustNotHandleProcessCorruptingExceptions|
|CheckId|CA2139|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Transparentní metoda je označena <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno jakoukoli metodu, která je transparentní a pokusí se zpracovat výjimku poškozující pomocí proces <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut. Výjimka poškozující proces je klasifikace CLR verze 4.0 výjimek takové <xref:System.AccessViolationException>. Atribut HandleProcessCorruptedStateExceptionsAttribute lze použít pouze metodami kritickými pro bezpečnost a bude ignorován, je-li použit u transparentních metod. Zpracování výjimek poskozeny procesu, musí být tato metoda zabezpečení kritické nebo bezpečně kritické.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut nebo označte metody <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V tomto příkladu je transparentní metodě označené <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut a se nezdaří pravidlo. Metody by měly také být označené <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.

 [!code-csharp[FxCop.Security.CA2139.TransparentMethodsMustNotHandleProcessCorruptingExceptions#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2139.transparentmethodsmustnothandleprocesscorruptingexceptions/cs/ca2139 - transparentmethodsmustnothandleprocesscorruptingexceptions.cs#1)]

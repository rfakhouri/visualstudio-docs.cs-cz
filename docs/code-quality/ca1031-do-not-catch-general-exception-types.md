---
title: 'CA1031: Nezachycujte výjimky obecného typu'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
helpviewer_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
ms.assetid: cbc283ae-2a46-4ec0-940e-85aa189b118f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb251798d4e1908c31d19356e711215baa52929d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031: Nezachycujte výjimky obecného typu
|||
|-|-|
|TypeName|DoNotCatchGeneralExceptionTypes|
|CheckId|CA1031|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 K obecné výjimce, jako <xref:System.Exception?displayProperty=fullName> nebo <xref:System.SystemException?displayProperty=fullName> je místo zachycení `catch` příkaz nebo klauzuli obecné catch jako `catch()` se používá.

## <a name="rule-description"></a>Popis pravidla
 Obecné výjimky by neměly být zachycovány.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, zachycení konkrétnější výjimky nebo opětovné obecné výjimky jako poslední příkaz v `catch` bloku.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Zachytávání nezachycujte výjimky obecného typu problémy běhové knihovny uživatele můžete skrýt a může ztížit ladění.

> [!NOTE]
>  Od verze [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)], modul CLR (CLR) již dodává výjimky v poškozeném stavu, ke kterým došlo v operačního systému a spravovaného kódu, například porušení přístupu v [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)], zpracovávat spravovaného kódu. Pokud chcete kompilaci aplikace ve [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] nebo novější verze a Udržovat zpracování výjimky v poškozeném stavu, můžete použít <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut metoda, která zpracovává výjimku v poškozeném stavu.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který je v rozporu toto pravidlo a typ, který implementuje správně `catch` bloku.

 [!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CPP/ca1031-do-not-catch-general-exception-types_1.cpp)]
 [!code-vb[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/VisualBasic/ca1031-do-not-catch-general-exception-types_1.vb)]
 [!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CSharp/ca1031-do-not-catch-general-exception-types_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2200: Znovu vyvolejte pro zachování podrobností zásobníku](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)
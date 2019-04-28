---
title: 'CA1031: Nezachycujte výjimky obecného typu'
ms.date: 11/04/2016
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
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e285ead27b8d3d7c674a138d5f06c69a7e88d1fc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779277"
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031: Nezachycujte výjimky obecného typu

|||
|-|-|
|TypeName|DoNotCatchGeneralExceptionTypes|
|CheckId|CA1031|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Obecná výjimka jako například <xref:System.Exception?displayProperty=fullName> nebo <xref:System.SystemException?displayProperty=fullName> je zachycena v `catch` příkazu nebo obecnou klauzulí catch, jako `catch()` se používá.

## <a name="rule-description"></a>Popis pravidla
 Obecné výjimky by neměly být zachycovány.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zachycení více specifické výjimky nebo znovu vyvolejte obecnou výjimku jako poslední příkaz v `catch` bloku.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Zachycení výjimky obecného typu může skrýt problémy za běhu z knihovny uživatele a může ztížit ladění.

> [!NOTE]
> Počínaje [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)], modul CLR (CLR) poskytuje už výjimky v poškozeném stavu, ke kterým dochází v operačním systému a spravovaného kódu, jako je například porušení přístupu v [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)], zpracovávat spravovaného kódu. Pokud chcete kompilovat aplikace [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] nebo novější verze a Udržovat zpracování výjimek v poškozeném stavu, můžete použít <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atributu na metodu, která zpracovává výjimku v poškozeném stavu.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje tato pravidla a typ, který implementuje správně `catch` bloku.

 [!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CPP/ca1031-do-not-catch-general-exception-types_1.cpp)]
 [!code-vb[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/VisualBasic/ca1031-do-not-catch-general-exception-types_1.vb)]
 [!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CSharp/ca1031-do-not-catch-general-exception-types_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA2200: Znovu vyvolejte pro zachování podrobností zásobníku](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)
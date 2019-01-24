---
title: 'CA1026: Nesmí být použity výchozí parametry | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
helpviewer_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
ms.assetid: 09643415-36ef-4d0f-9411-5721e14e2512
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 25e38f6db5caa6b797774463552cd17fd07bdf5d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54784126"
---
# <a name="ca1026-default-parameters-should-not-be-used"></a>CA1026: Neměly by být použity výchozí parametry
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DefaultParametersShouldNotBeUsed|
|CheckId|CA1026|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Externě viditelný typ obsahuje externě viditelná metoda, která používá výchozí parametr.

## <a name="rule-description"></a>Popis pravidla
 Metody používající výchozí parametry jsou povoleny v rámci specifikace CLS (Common Language); ale specifikace CLS umožňuje kompilátorům Ignorovat hodnoty přiřazené těmto parametrům. Kód, který je napsán pro kompilátory, které ignorovat výchozí hodnoty parametrů musíte explicitně zadat argumenty pro každý parametr výchozí. Chcete-li zachovat shodné chování napříč programovacími jazyky, by měl vyměnit metody používající výchozí parametry přetížením metody, která výchozí parametry poskytují.

 Kompilátor ignoruje hodnoty výchozí parametry pro spravované rozšíření jazyka C++ při přístupu ke spravovaným kódem. Kompilátor jazyka Visual Basic podporuje metody, které mají výchozí parametry, které používají [volitelné](http://msdn.microsoft.com/library/4571ce88-a539-4115-b230-54eb277c6aa7) – klíčové slovo.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, nahraďte metody používající výchozí parametry přetížením metody, které poskytují výchozí parametry.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která používá výchozí hodnoty parametrů a přetížené metody, které poskytují ekvivalentní funkce.

 [!code-vb[FxCop.Design.DefaultParameters#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.DefaultParameters/vb/FxCop.Design.DefaultParameters.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1025: Nahraďte opakované argumenty polem](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)

## <a name="see-also"></a>Viz také
 [Jazyková nezávislost a jazykově nezávislé komponenty](http://msdn.microsoft.com/library/4f0b77d0-4844-464f-af73-6e06bedeafc6)

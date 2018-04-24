---
title: 'CA2101: Určete zařazování pro argumenty řetězce volání P'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8171c318d419edc49410c44d381e82f088014082
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2101-specify-marshaling-for-pinvoke-string-arguments"></a>CA2101: Určete zařazování pro argumenty řetězce volání nespravovaného kódu
|||
|-|-|
|TypeName|SpecifyMarshalingForPInvokeStringArguments|
|CheckId|CA2101|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Vyvolání platformy člen umožňuje částečně důvěryhodné volající má řetězcový parametr a není explicitně zařazování řetězec.

## <a name="rule-description"></a>Popis pravidla
 Při převodu z kódu Unicode na ANSI je možné, že ne všechny znaky znakové sady Unicode představovat v konkrétní stránky kódu ANSI. *Přizpůsobená mapování* pokusí nahraďte znak znaku, který nelze vyřešit tento problém. Použití této funkce může způsobit potenciální ohrožení zabezpečení, protože nemůže ovládat znak, který je vybrán. Například může vytvořit škodlivý kód záměrně řetězec znaků Unicode, který obsahuje znaky, které nejsou k dispozici v konkrétní znakové stránky, které jsou převedeny na souboru systému speciální znaky, jako například '..' nebo '/'. Všimněte si také, že kontrola zabezpečení pro speciální znaky často udělat předtím, než je daný řetězec převést na ANSI.

 Přizpůsobená mapování je výchozí pro převod z nespravovaných WChar k MByte. Pokud je například možné mapování explicitně zakázat, kód může obsahovat ohrožení zabezpečení využitelných kvůli tomuto problému.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, explicitně zařazování řetězce.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která porušuje toto pravidlo a pak ukazuje, jak opravit porušení zásady.

 [!code-csharp[FxCop.Security.PinvokeAnsiUnicode#1](../code-quality/codesnippet/CSharp/ca2101-specify-marshaling-for-p-invoke-string-arguments_1.cs)]
---
title: "CA2101: Určete zařazování pro argumenty řetězce volání P | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 15191983d08bfc99848e4a16c0059c075b234bb3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
---
title: 'CA2101: Určete zařazování pro argumenty řetězce volání | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 11916609f2efa9c0b6e208548ba51795bd276015
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68154389"
---
# <a name="ca2101-specify-marshaling-for-pinvoke-string-arguments"></a>CA2101: Určete zařazování pro argumenty řetězce volání nespravovaného kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SpecifyMarshalingForPInvokeStringArguments|
|CheckId|CA2101|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Vyvolání platformy člen umožňuje částečně důvěryhodné volající, má řetězcový parametr a explicitně nezařazuje řetězec.

## <a name="rule-description"></a>Popis pravidla
 Při převodu z Unicode na ANSI je možné, že ne všechny znaky Unicode mohou být zastoupeny v konkrétní znakovou stránku ANSI. *Nejlepšího mapování* pokusí o vyřešení tohoto problému nahrazením znaku znaku, který nejde reprezentovat. Použití této funkce může způsobit potenciální ohrožení zabezpečení, protože nelze určit, na znak, který je vybrán. Například, škodlivý kód záměrně vytvořit řetězec znaků Unicode, který obsahuje znaky, které nebyly nalezeny v konkrétní kódové stránky, které jsou převedeny na souboru systému speciální znaky, jako například '..' nebo '/'. Všimněte si také, že kontroly zabezpečení pro zvláštní znaky často dochází před daný řetězec převést na ANSI.

 Nejlepšího mapování je výchozí nastavení pro nespravované převod WChar k MByte. Pokud není explicitně zakázat nejlepšího mapování, může kód obsahovat chybu zneužitelné zabezpečení kvůli tomuto problému.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zařaďte explicitně řetězcovými datovými typy.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která porušuje pravidlo a pak ukazuje, jak vyřešit porušení zásady.

 [!code-csharp[FxCop.Security.PinvokeAnsiUnicode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.PinvokeAnsiUnicode/cs/FxCop.Security.PinvokeAnsiUnicode.cs#1)]

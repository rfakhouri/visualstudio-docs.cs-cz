---
title: 'CA1032: Implementujte standardní konstruktory výjimky'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1032
- ImplementStandardExceptionConstructors
helpviewer_keywords:
- CA1032
- ImplementStandardExceptionConstructors
ms.assetid: a8623c56-273a-4c95-8d83-95911a042be7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7baf13eb9125b273ad8fb1265a65eb7b053238a1
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55922386"
---
# <a name="ca1032-implement-standard-exception-constructors"></a>CA1032: Implementujte standardní konstruktory výjimky

|||
|-|-|
|TypeName|ImplementStandardExceptionConstructors|
|CheckId|CA1032|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Typ rozšiřuje <xref:System.Exception?displayProperty=fullName> ale nebude deklarovat všechny požadované konstruktory.

## <a name="rule-description"></a>Popis pravidla

Typy výjimek musí implementovat následující tři konstruktory:

- public NewException()

- veřejné NewException(string)

- veřejné NewException (string, výjimka)

Kromě toho pokud používáte starší verzi FxCop statickou analýzu kódu jako rozdíl od [analyzátory FxCop založené na platformě Roslyn](../code-quality/roslyn-analyzers-overview.md), neexistence čtvrtý konstruktor také vygeneruje porušení:

- chráněná nebo privátní NewException (SerializationInfo, StreamingContext)

Není-li dodána úplná sada konstruktorů, může být obtížné správně ošetřit výjimky. Například konstruktor, který nemá podpis `NewException(string, Exception)` slouží k vytvoření výjimky, které jsou způsobeny další výjimky. Bez tohoto konstruktoru nelze vytvořit a vyvolat instance vlastní výjimky, která obsahuje vnitřní výjimka (vnořené), který je spravovaný kód by měl provést v takové situaci.

První tři výjimka konstruktory jsou veřejné konvencí. Čtvrtý konstruktor je chráněný v nezapečetěné třídy a soukromý v třídách sealed. Další informace najdete v tématu [CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, přidejte chybějící konstruktory s výjimkou a ujistěte se, že mají správnou usnadnění.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla při porušení zásad je způsobena použitím úroveň různý přístup pro veřejné konstruktory. Kromě toho je možné potlačení upozornění pro `NewException(SerializationInfo, StreamingContext)` konstruktor využijete při vytváření přenosnou knihovnou tříd (PCL).

## <a name="example"></a>Příklad

Následující příklad obsahuje typ výjimky, která porušuje pravidlo a typ výjimky, která je implementována správně.

[!code-csharp[FxCop.Design.ExceptionMultipleCtors#1](../code-quality/codesnippet/CSharp/ca1032-implement-standard-exception-constructors_1.cs)]

## <a name="see-also"></a>Viz také:

[CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)
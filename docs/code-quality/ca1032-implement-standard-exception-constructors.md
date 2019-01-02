---
title: 'CA1032: Implementujte standardní konstruktory výjimky'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c0a9439150602bdb3f84f9a82aacac39dc2e9517
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53881228"
---
# <a name="ca1032-implement-standard-exception-constructors"></a>CA1032: Implementujte standardní konstruktory výjimky

|||
|-|-|
|TypeName|ImplementStandardExceptionConstructors|
|CheckId|CA1032|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Typ rozšiřuje <xref:System.Exception?displayProperty=fullName> ale nebude deklarovat všechny požadované konstruktory.

## <a name="rule-description"></a>Popis pravidla

Typy výjimek musí implementovat následující tři konstruktory:

- veřejné NewException()

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
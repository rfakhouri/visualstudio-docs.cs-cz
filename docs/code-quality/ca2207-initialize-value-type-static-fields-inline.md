---
title: 'CA2207: Inicializujte statická pole s typem hodnoty vloženě'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fb75c6d06502c9d2fac437a8924af4d51ddd6d0a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55036157"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: Inicializujte statická pole s typem hodnoty vloženě

|||
|-|-|
|TypeName|InitializeValueTypeStaticFieldsInline|
|CheckId|CA2207|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina
 Hodnotový typ deklaruje explicitní statický konstruktor.

## <a name="rule-description"></a>Popis pravidla
 Při deklaraci value-type. při inicializaci výchozí, pokud všechna pole typu hodnoty jsou nastavené na hodnotu nula a všechna pole typu odkazu jsou nastaveny na `null` (`Nothing` v jazyce Visual Basic). Explicitní statický konstruktor je zaručeno, se spustí před konstruktor instance nebo volá statický člen typu. Proto pokud typ je vytvořen bez nutnosti volat konstruktor instance, statický konstruktor není zaručeno, že ke spuštění.

 Pokud všechna statická data je vložená inicializována a je deklarována bez explicitní statický konstruktor, kompilátory jazyků C# a Visual Basic přidejte `beforefieldinit` příznak do definice třídy jazyka MSIL. Kompilátory taky přidat privátní statický konstruktor, který obsahuje kód Statická inicializace. Tato privátní statický konstruktor se zaručeně spustí předtím, než jsou přístupné všechny statické pole typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li vyřešit porušení tohoto pravidla inicializujte všechna statická data, když je deklarovaný a statický konstruktor odeberte.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="related-rules"></a>Související pravidla
 [CA1810: Inicializujte odkazový typ statického pole vloženě](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)